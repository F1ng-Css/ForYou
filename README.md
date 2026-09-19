@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;700&family=Playfair+Display:ital,wght@0,500;0,600;1,500&family=Caveat:wght@500;600&display=swap');

*{box-sizing:border-box;margin:0;padding:0}
:root{
  --cream:#fff9ed;
  --green:#55734b;
  --dark-green:#29452d;
  --yellow:#f5b72e;
  --soft-yellow:#ffe8a6;
  --pink:#e8a7a1;
}
body{
  min-height:100vh;
  overflow-x:hidden;
  color:var(--dark-green);
  font-family:'DM Sans',sans-serif;
  background:
    radial-gradient(circle at 18% 18%, rgba(255,235,164,.9), transparent 25%),
    radial-gradient(circle at 85% 12%, rgba(255,205,155,.6), transparent 22%),
    linear-gradient(135deg,#fffdf4 0%,#f5f2d9 48%,#e4efd9 100%);
  position:relative;
}
body:before{
  content:"";
  position:fixed;inset:0;pointer-events:none;z-index:10;opacity:.18;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.8' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.12'/%3E%3C/svg%3E");
}
.scene{min-height:100vh;position:relative;padding:50px 20px 70px;display:grid;place-items:center}
.sun{position:absolute;width:430px;height:430px;border-radius:50%;right:-130px;top:-150px;
  background:radial-gradient(circle,rgba(255,222,110,.72),rgba(255,222,110,.16) 48%,transparent 70%);
  filter:blur(3px);animation:sunPulse 5s ease-in-out infinite}
.grass{position:fixed;left:-5%;right:-5%;bottom:-65px;height:160px;background:#78945e;
  border-radius:50% 50% 0 0/35% 35% 0 0;opacity:.78;z-index:0}
.grass:before,.grass:after{content:"";position:absolute;bottom:35px;width:70px;height:110px;border-left:3px solid #52724a;border-radius:100% 0 0 0;transform:rotate(-18deg)}
.grass:before{left:12%} .grass:after{right:16%;transform:scaleX(-1) rotate(-18deg)}

.card{position:relative;z-index:2;width:min(1040px,100%);display:grid;grid-template-columns:1fr 1fr;
  gap:42px;align-items:center;padding:38px;border:1px solid rgba(255,255,255,.8);
  border-radius:34px;background:rgba(255,255,255,.56);backdrop-filter:blur(15px);
  box-shadow:0 28px 70px rgba(77,91,49,.18);animation:appear 1s ease both}
.photo-wrap{position:relative;display:flex;justify-content:center;animation:float 6s ease-in-out infinite}
.photo-wrap:before{content:"";position:absolute;inset:5% 8%;border-radius:22px;
  background:linear-gradient(160deg,#dff0ff,#f5b72e 78%);transform:rotate(-4deg);
  box-shadow:0 18px 34px rgba(40,70,100,.18)}
.photo{position:relative;width:min(100%,380px);max-height:64vh;object-fit:cover;
  aspect-ratio:4/5;border-radius:22px;display:block;
  box-shadow:0 24px 46px rgba(20,40,70,.28);transform:rotate(2deg);border:9px solid #fffdf7}
.photo-tag{position:absolute;bottom:-14px;right:8%;z-index:4;background:#fffdf7;color:#7c6330;
  font-family:'Caveat',cursive;font-size:22px;line-height:1;padding:8px 16px 6px;border-radius:12px;
  box-shadow:0 8px 18px rgba(60,50,20,.18);transform:rotate(-3deg)}
.doodle-ring{position:absolute;inset:-4%;pointer-events:none;z-index:2;opacity:.9;
  animation:ringPulse 6s ease-in-out infinite}
.doodle-ring svg{width:100%;height:100%}
.sticker{position:absolute;z-index:3;font-size:34px;filter:drop-shadow(0 5px 5px rgba(0,0,0,.08))}
.s1{left:2%;top:7%;animation:wiggle 3s ease-in-out infinite}
.s2{right:3%;bottom:9%;animation:wiggle 4s .5s ease-in-out infinite}
.doodle{position:fixed;pointer-events:none;z-index:1;color:#fff;opacity:0;
  filter:drop-shadow(0 2px 4px rgba(0,0,0,.06));animation:doodlePop 5s ease-in-out infinite}
.mariposa{position:fixed;pointer-events:none;z-index:1;animation:volar linear infinite}
.mariposa svg{width:100%;height:auto;animation:aletazo 3s ease-in-out infinite}
.ala{transform-origin:50% 50%;animation:aletear .3s ease-in-out infinite alternate}
.content{padding:15px 10px 15px 0}
.eyebrow{letter-spacing:4px;text-transform:uppercase;font-size:12px;font-weight:700;color:#8b7134;margin-bottom:16px}
h1{font-family:'Playfair Display',serif;font-size:clamp(42px,6vw,70px);line-height:.98;font-weight:600;margin-bottom:22px}
h1 span{color:#d89b19}
.message{font-size:17px;line-height:1.8;color:#52604a;max-width:510px}
.signature{margin-top:27px;font-family:'Playfair Display',serif;font-size:25px;color:#7c6330}
.btn{margin-top:28px;border:0;border-radius:999px;padding:14px 23px;background:#fff8df;color:#665021;
  font:700 14px 'DM Sans';cursor:pointer;box-shadow:0 8px 22px rgba(95,76,28,.12);transition:.25s}
.btn:hover{transform:translateY(-3px) scale(1.02);box-shadow:0 12px 28px rgba(95,76,28,.18)}
#secret{max-height:0;overflow:hidden;opacity:0;transition:max-height .8s ease,opacity .8s ease;margin-top:0}
#secret.open{max-height:180px;opacity:1;margin-top:22px}
.secret-text{padding:17px 19px;border-left:3px solid var(--yellow);background:rgba(255,249,224,.7);border-radius:0 15px 15px 0;line-height:1.7}
.petal,.sparkle,.butterfly{position:fixed;pointer-events:none;z-index:1}
.petal{top:-40px;font-size:22px;animation:fall linear infinite;opacity:.72}
.p1{left:8%;animation-duration:9s;animation-delay:-2s} .p2{left:24%;animation-duration:12s;animation-delay:-7s}
.p3{left:48%;animation-duration:10s;animation-delay:-4s} .p4{left:70%;animation-duration:13s;animation-delay:-9s}
.p5{left:88%;animation-duration:11s;animation-delay:-5s}
.sparkle{color:#fff;font-size:25px;animation:twinkle 2.4s ease-in-out infinite}
.sp1{top:17%;left:7%} .sp2{top:30%;right:7%;animation-delay:.8s} .sp3{bottom:20%;left:48%;animation-delay:1.3s}
.butterfly{font-size:28px;animation:fly 8s ease-in-out infinite}
.b1{left:3%;top:58%} .b2{right:2%;top:42%;animation-delay:-4s;font-size:24px}
.burst{position:fixed;inset:0;pointer-events:none;z-index:20}
.burst span{position:absolute;left:50%;top:50%;font-size:24px;animation:burst 1.3s ease-out forwards}

@keyframes appear{from{opacity:0;transform:translateY(25px) scale(.98)}to{opacity:1;transform:none}}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-10px)}}
@keyframes sunPulse{0%,100%{transform:scale(1);opacity:.8}50%{transform:scale(1.08);opacity:1}}
@keyframes fall{0%{transform:translate3d(0,-50px,0) rotate(0)}50%{transform:translate3d(70px,50vh,0) rotate(180deg)}100%{transform:translate3d(-40px,110vh,0) rotate(360deg)}}
@keyframes twinkle{0%,100%{opacity:.25;transform:scale(.7) rotate(0)}50%{opacity:1;transform:scale(1.2) rotate(18deg)}}
@keyframes wiggle{0%,100%{transform:rotate(-4deg)}50%{transform:rotate(5deg)}}
@keyframes fly{0%,100%{transform:translate(0,0) rotate(-8deg)}50%{transform:translate(45px,-25px) rotate(8deg)}}
@keyframes burst{0%{transform:translate(-50%,-50%) scale(.5);opacity:1}100%{transform:translate(calc(-50% + var(--x)),calc(-50% + var(--y))) rotate(180deg);opacity:0}}
@keyframes ringPulse{0%,100%{transform:scale(1) rotate(0deg);opacity:.85}50%{transform:scale(1.03) rotate(1deg);opacity:1}}
@keyframes doodlePop{0%,100%{opacity:0;transform:scale(.55)}45%,60%{opacity:.8;transform:scale(1)}}
@keyframes volar{0%{transform:translate(-12vw,0)}100%{transform:translate(112vw,0)}}
@keyframes aletazo{0%,100%{transform:translateY(-14px) rotate(-5deg)}50%{transform:translateY(14px) rotate(5deg)}}
@keyframes aletear{from{transform:scaleX(1)}to{transform:scaleX(.35)}}

@media(max-width:800px){
  .scene{padding:25px 14px 80px}
  .card{grid-template-columns:1fr;gap:25px;padding:22px;border-radius:25px}
  .content{padding:0 5px 10px}
  .photo{max-height:52vh;width:min(78vw,320px)}
  h1{font-size:48px}
  .message{font-size:15px}
  .sun{width:300px;height:300px}
}
