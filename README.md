<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vonvati World Academy — Escuela de Baile en Guadalajara</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;font-size:16px}
body{font-family:'Outfit',sans-serif;background:#f8f7f5;color:#0d0d0d;overflow-x:hidden}

:root{
  --ink:#0d0d0d;
  --cream:#f8f7f5;
  --white:#ffffff;
  --red:#c8102e;
  --red2:#a50d24;
  --gray:#888;
  --light:#eeece9;
  --serif:'Playfair Display',Georgia,serif;
  --sans:'Outfit',sans-serif;
}

/* ═══ NAV ═══ */
nav{
  position:fixed;top:0;left:0;width:100%;z-index:200;
  display:flex;align-items:center;justify-content:space-between;
  padding:20px 6%;
  transition:background .4s,padding .4s,box-shadow .4s;
}
nav.scrolled{
  background:rgba(13,13,13,.97);
  padding:14px 6%;
  box-shadow:0 2px 40px rgba(0,0,0,.3);
  backdrop-filter:blur(10px);
}
.nav-logo{
  font-family:var(--serif);font-size:1.5rem;font-weight:700;
  color:var(--white);text-decoration:none;letter-spacing:.02em;
}
.nav-logo span{color:var(--red)}
.nav-links{display:flex;gap:36px;list-style:none;align-items:center}
.nav-links a{
  color:rgba(255,255,255,.7);text-decoration:none;
  font-size:.78rem;letter-spacing:.14em;text-transform:uppercase;font-weight:500;
  transition:color .2s;
}
.nav-links a:hover{color:#fff}
.nav-pill{
  background:var(--red);color:#fff !important;
  padding:9px 22px;border-radius:100px !important;
}
.nav-pill:hover{background:var(--red2) !important}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;padding:4px}
.hamburger span{display:block;width:22px;height:1.5px;background:#fff;transition:transform .3s,opacity .3s}
.hamburger.open span:nth-child(1){transform:translateY(6.5px) rotate(45deg)}
.hamburger.open span:nth-child(2){opacity:0}
.hamburger.open span:nth-child(3){transform:translateY(-6.5px) rotate(-45deg)}

/* Mobile menu */
#mob-menu{
  display:none;position:fixed;inset:0;background:rgba(13,13,13,.99);
  z-index:190;flex-direction:column;align-items:center;justify-content:center;gap:30px;
}
#mob-menu a{
  color:rgba(255,255,255,.8);text-decoration:none;font-size:1.3rem;
  letter-spacing:.1em;text-transform:uppercase;font-weight:300;
  transition:color .2s;
}
#mob-menu a:hover{color:#fff}
#mob-menu .mob-cta{
  margin-top:10px;background:var(--red);color:#fff !important;
  padding:14px 40px;border-radius:100px;font-size:.9rem;font-weight:600;letter-spacing:.1em;
}

/* ═══ HERO ═══ */
#hero{
  min-height:100vh;position:relative;
  display:flex;align-items:flex-end;
  overflow:hidden;background:#0d0d0d;
}
.hero-img{
  position:absolute;inset:0;
  background:url('https://images.unsplash.com/photo-1545959570-a94084071b5d?w=1800&q=80&fit=crop') center/cover no-repeat;
  transform:scale(1.04);
  animation:heroZoom 12s ease-out forwards;
}
@keyframes heroZoom{to{transform:scale(1)}}
.hero-overlay{
  position:absolute;inset:0;
  background:linear-gradient(to top, rgba(13,13,13,.95) 0%, rgba(13,13,13,.55) 50%, rgba(13,13,13,.2) 100%);
}
.hero-body{
  position:relative;z-index:2;
  width:100%;padding:0 6% 80px;
  display:flex;align-items:flex-end;justify-content:space-between;
  flex-wrap:wrap;gap:40px;
}
.hero-left{max-width:680px}
.hero-tag{
  display:inline-flex;align-items:center;gap:10px;
  font-size:.7rem;letter-spacing:.22em;text-transform:uppercase;
  color:var(--red);font-weight:600;margin-bottom:24px;
  opacity:0;animation:slideUp .8s .3s forwards;
}
.hero-tag::before{content:'';width:30px;height:1px;background:var(--red)}
h1.hero-h{
  font-family:var(--serif);
  font-size:clamp(3.5rem,7.5vw,7rem);
  font-weight:900;line-height:.95;
  color:#fff;margin-bottom:28px;
  opacity:0;animation:slideUp .9s .45s forwards;
}
h1.hero-h em{
  font-style:italic;font-weight:400;
  color:transparent;
  -webkit-text-stroke:1.5px rgba(255,255,255,.6);
}
.hero-sub{
  font-size:1.05rem;line-height:1.75;color:rgba(255,255,255,.55);
  max-width:440px;margin-bottom:40px;
  opacity:0;animation:slideUp .9s .6s forwards;
}
.hero-btns{
  display:flex;gap:14px;flex-wrap:wrap;
  opacity:0;animation:slideUp .9s .75s forwards;
}
.btn-red{
  background:var(--red);color:#fff;border:none;border-radius:100px;
  padding:16px 38px;font-size:.8rem;letter-spacing:.13em;text-transform:uppercase;
  font-weight:600;cursor:pointer;text-decoration:none;display:inline-flex;align-items:center;gap:8px;
  transition:background .25s,transform .2s,box-shadow .25s;
  font-family:var(--sans);
}
.btn-red:hover{background:var(--red2);transform:translateY(-2px);box-shadow:0 12px 32px rgba(200,16,46,.4)}
.btn-ghost{
  background:transparent;color:rgba(255,255,255,.75);
  border:1px solid rgba(255,255,255,.25);border-radius:100px;
  padding:15px 34px;font-size:.8rem;letter-spacing:.13em;text-transform:uppercase;
  font-weight:500;cursor:pointer;text-decoration:none;display:inline-block;
  transition:border-color .25s,color .25s;
  font-family:var(--sans);
}
.btn-ghost:hover{border-color:rgba(255,255,255,.7);color:#fff}
.hero-right{
  display:flex;flex-direction:column;gap:20px;align-items:flex-end;
  opacity:0;animation:slideUp .9s .9s forwards;
}
.hero-stat{text-align:right}
.hero-stat-n{
  font-family:var(--serif);font-size:3rem;font-weight:900;color:#fff;line-height:1;
}
.hero-stat-n span{color:var(--red)}
.hero-stat-l{font-size:.68rem;letter-spacing:.16em;text-transform:uppercase;color:rgba(255,255,255,.35);margin-top:3px}
.hero-scroll{
  position:absolute;bottom:32px;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:8px;
  color:rgba(255,255,255,.3);font-size:.65rem;letter-spacing:.2em;text-transform:uppercase;
  opacity:0;animation:slideUp .8s 1.2s forwards;
}
.scroll-line{width:1px;height:40px;background:rgba(255,255,255,.15);animation:scrollAnim 2s infinite}
@keyframes scrollAnim{
  0%{transform:scaleY(0);transform-origin:top}
  50%{transform:scaleY(1);transform-origin:top}
  51%{transform:scaleY(1);transform-origin:bottom}
  100%{transform:scaleY(0);transform-origin:bottom}
}
@keyframes slideUp{
  from{opacity:0;transform:translateY(30px)}
  to{opacity:1;transform:translateY(0)}
}

/* ═══ SHARED SECTION STYLES ═══ */
.section-label{
  font-size:.68rem;letter-spacing:.24em;text-transform:uppercase;
  color:var(--red);font-weight:600;
  display:flex;align-items:center;gap:10px;margin-bottom:16px;
}
.section-label::before{content:'';width:26px;height:1px;background:var(--red)}
h2.s-title{
  font-family:var(--serif);
  font-size:clamp(2rem,4vw,3.4rem);
  font-weight:700;line-height:1.1;margin-bottom:20px;
}
h2.s-title em{font-style:italic;font-weight:400}
.red-bar{width:44px;height:3px;background:var(--red);margin:24px 0}

/* Reveal */
.rv{opacity:0;transform:translateY(36px);transition:opacity .75s,transform .75s}
.rv.in{opacity:1;transform:none}
.rv.d1{transition-delay:.1s}
.rv.d2{transition-delay:.2s}
.rv.d3{transition-delay:.3s}
.rv.d4{transition-delay:.4s}

/* ═══ ABOUT ═══ */
#about{padding:110px 6%;background:var(--white)}
.about-wrap{
  display:grid;grid-template-columns:1fr 1.1fr;gap:80px;
  max-width:1200px;align-items:center;
}
.about-text p{font-size:.97rem;line-height:1.85;color:#555;margin-bottom:18px}
.about-img-grid{
  display:grid;grid-template-columns:1fr 1fr;grid-template-rows:260px 200px;
  gap:12px;
}
.ab-img{overflow:hidden;border-radius:6px;position:relative}
.ab-img img{width:100%;height:100%;object-fit:cover;transition:transform .6s;display:block}
.ab-img:hover img{transform:scale(1.06)}
.ab-img.tall{grid-row:1/3}
.about-pills{display:flex;flex-direction:column;gap:12px;margin-top:32px}
.pill{
  display:flex;align-items:center;gap:12px;
  font-size:.87rem;color:#444;padding:12px 16px;
  background:var(--light);border-radius:6px;
}
.pill-dot{width:7px;height:7px;background:var(--red);border-radius:50%;flex-shrink:0}

/* ═══ CLASSES ═══ */
#classes{padding:110px 6%;background:var(--ink)}
#classes h2.s-title{color:#fff}
.classes-top{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:52px;flex-wrap:wrap;gap:20px}
.classes-top p{color:rgba(255,255,255,.45);max-width:380px;line-height:1.7;font-size:.95rem}
.classes-scroll{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:3px;max-width:1400px;
}
.cls-card{
  position:relative;overflow:hidden;aspect-ratio:3/4;cursor:pointer;
  background:#111;
}
.cls-card img{
  width:100%;height:100%;object-fit:cover;
  transition:transform .6s;filter:brightness(.6) saturate(.8);
  display:block;
}
.cls-card:hover img{transform:scale(1.08);filter:brightness(.4) saturate(.6)}
.cls-overlay{
  position:absolute;inset:0;
  background:linear-gradient(to top,rgba(13,13,13,.9) 0%,transparent 55%);
}
.cls-content{
  position:absolute;bottom:0;left:0;right:0;
  padding:28px 24px;
  transition:transform .4s;
}
.cls-card:hover .cls-content{transform:translateY(-8px)}
.cls-tag{
  display:inline-block;font-size:.62rem;letter-spacing:.16em;text-transform:uppercase;
  color:var(--red);border:1px solid rgba(200,16,46,.5);padding:3px 9px;border-radius:100px;
  margin-bottom:10px;
}
.cls-name{
  font-family:var(--serif);font-size:1.5rem;font-weight:700;color:#fff;
  margin-bottom:6px;line-height:1.1;
}
.cls-desc{
  font-size:.8rem;color:rgba(255,255,255,0);
  line-height:1.6;max-height:0;overflow:hidden;
  transition:color .3s,max-height .4s;
}
.cls-card:hover .cls-desc{color:rgba(255,255,255,.6);max-height:80px}
.cls-kids{
  grid-column:span 2;aspect-ratio:auto;height:240px;
}

/* ═══ PRICING ═══ */
#pricing{padding:110px 6%;background:var(--cream)}
.pricing-intro{max-width:560px;margin-bottom:60px}
.pricing-intro p{font-size:.97rem;color:#666;line-height:1.75}
.pricing-grid{
  display:grid;grid-template-columns:repeat(3,1fr);
  gap:20px;max-width:1200px;
}
.p-card{
  background:#fff;border:1px solid #e8e6e3;border-radius:12px;
  padding:36px 30px;position:relative;
  transition:box-shadow .3s,transform .3s;
}
.p-card:hover{box-shadow:0 20px 60px rgba(0,0,0,.09);transform:translateY(-5px)}
.p-card.hot{background:var(--ink);border-color:var(--ink);color:#fff}
.hot-tag{
  position:absolute;top:-1px;right:28px;
  background:var(--red);color:#fff;font-size:.62rem;
  letter-spacing:.14em;text-transform:uppercase;padding:5px 14px;
  border-radius:0 0 8px 8px;font-weight:600;
}
.p-label{font-size:.68rem;letter-spacing:.18em;text-transform:uppercase;color:#aaa;margin-bottom:16px}
.p-card.hot .p-label{color:rgba(255,255,255,.35)}
.p-price{
  font-family:var(--serif);font-size:3rem;font-weight:900;
  color:var(--ink);line-height:1;margin-bottom:4px;
}
.p-card.hot .p-price{color:#fff}
.p-price sup{font-size:1.2rem;vertical-align:super}
.p-period{font-size:.78rem;color:#aaa;margin-bottom:22px}
.p-card.hot .p-period{color:rgba(255,255,255,.4)}
.p-line{height:1px;background:#f0ece8;margin:18px 0}
.p-card.hot .p-line{background:rgba(255,255,255,.1)}
.p-feats{display:flex;flex-direction:column;gap:10px;margin-bottom:28px}
.p-feat{display:flex;gap:10px;font-size:.84rem;color:#555;align-items:flex-start}
.p-card.hot .p-feat{color:rgba(255,255,255,.65)}
.p-feat .ck{color:var(--red);flex-shrink:0;margin-top:1px}
.p-btn{
  display:block;text-align:center;background:var(--ink);color:#fff;
  padding:14px;border-radius:100px;font-size:.76rem;letter-spacing:.12em;
  text-transform:uppercase;text-decoration:none;font-weight:600;
  transition:background .25s;
}
.p-btn:hover{background:#333}
.p-card.hot .p-btn{background:var(--red)}
.p-card.hot .p-btn:hover{background:var(--red2)}
.pricing-note{
  max-width:700px;margin:52px auto 0;text-align:center;
  font-size:.85rem;color:#999;line-height:1.7;
}

/* ═══ HOW ═══ */
#how{padding:110px 6%;background:#fff}
.how-grid{display:grid;grid-template-columns:1fr 1fr;gap:3px;max-width:1100px}
.how-card{
  padding:52px 44px;background:var(--cream);
  position:relative;overflow:hidden;
}
.how-card::before{
  content:'';position:absolute;top:0;left:0;
  width:3px;height:100%;background:var(--ink);
  transition:background .3s;
}
.how-card:hover::before{background:var(--red)}
.how-num{
  font-family:var(--serif);font-size:5rem;font-weight:900;
  color:var(--light);line-height:1;margin-bottom:16px;
}
.how-title{font-size:1.1rem;font-weight:600;margin-bottom:14px;color:var(--ink)}
.how-body{font-size:.88rem;color:#666;line-height:1.8}
.how-items{display:flex;flex-direction:column;gap:8px;margin-top:18px}
.how-item{display:flex;gap:10px;font-size:.85rem;color:#666}
.how-item::before{content:'—';color:var(--red);flex-shrink:0}

/* ═══ EXPERIENCE ═══ */
#experience{padding:0;background:var(--ink);overflow:hidden}
.exp-banner{
  position:relative;height:580px;
  background:url('https://images.unsplash.com/photo-1504609813442-a8924e83f76e?w=1800&q=80&fit=crop') center/cover no-repeat;
}
.exp-banner-ov{
  position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(13,13,13,.92) 0%,rgba(13,13,13,.5) 60%,rgba(200,16,46,.2) 100%);
}
.exp-banner-content{
  position:absolute;inset:0;
  display:flex;flex-direction:column;justify-content:center;
  padding:0 6%;max-width:680px;
}
.exp-banner-content h2{color:#fff;margin-bottom:24px}
.exp-banner-content p{color:rgba(255,255,255,.55);font-size:.97rem;line-height:1.8;margin-bottom:36px;max-width:440px}
.exp-cards{
  display:grid;grid-template-columns:repeat(3,1fr);
  border-top:1px solid rgba(255,255,255,.07);
}
.exp-c{
  padding:44px 36px;
  border-right:1px solid rgba(255,255,255,.07);
  transition:background .3s;
}
.exp-c:last-child{border:none}
.exp-c:hover{background:rgba(255,255,255,.03)}
.exp-icon{font-size:2rem;margin-bottom:18px}
.exp-name{
  font-family:var(--serif);font-size:1.35rem;font-weight:700;
  color:#fff;margin-bottom:10px;
}
.exp-desc{font-size:.83rem;color:rgba(255,255,255,.4);line-height:1.7}

/* ═══ GALLERY STRIP ═══ */
.gallery-strip{
  display:grid;grid-template-columns:repeat(5,1fr);
  height:300px;
  background:var(--ink);
}
.gs-img{overflow:hidden;position:relative}
.gs-img img{width:100%;height:100%;object-fit:cover;filter:brightness(.7) saturate(.7);transition:filter .5s,transform .5s;display:block}
.gs-img:hover img{filter:brightness(.5) saturate(.5);transform:scale(1.08)}
.gs-img::after{
  content:'';position:absolute;inset:0;
  background:rgba(13,13,13,.2);
}

/* ═══ REVIEWS ═══ */
#reviews{padding:110px 6%;background:var(--cream)}
.reviews-top{
  display:flex;align-items:flex-end;gap:32px;margin-bottom:56px;flex-wrap:wrap;
}
.big-score{
  font-family:var(--serif);font-size:7rem;font-weight:900;
  color:var(--ink);line-height:1;
}
.reviews-meta-col{padding-bottom:16px}
.stars-row{font-size:1.3rem;color:#f4b400;letter-spacing:3px;margin-bottom:6px}
.reviews-meta-col p{font-size:.82rem;color:#aaa}
.reviews-grid{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));
  gap:20px;max-width:1200px;
}
.rv-card{
  background:#fff;border-radius:10px;padding:28px;
  border:1px solid #ece9e5;
  transition:box-shadow .3s;
}
.rv-card:hover{box-shadow:0 12px 36px rgba(0,0,0,.07)}
.rv-head{display:flex;align-items:center;gap:14px;margin-bottom:14px}
.rv-av{
  width:44px;height:44px;border-radius:50%;
  background:var(--ink);color:#fff;
  display:flex;align-items:center;justify-content:center;
  font-family:var(--serif);font-size:1rem;font-weight:700;flex-shrink:0;
}
.rv-name{font-weight:600;font-size:.88rem}
.rv-date{font-size:.72rem;color:#bbb;margin-top:2px}
.rv-stars{font-size:.85rem;color:#f4b400;letter-spacing:2px;margin-bottom:10px}
.rv-text{font-size:.85rem;color:#666;line-height:1.7}

/* ═══ TESTIMONIALS ═══ */
#testimonials{padding:110px 6%;background:#fff}
.testi-grid{
  display:grid;grid-template-columns:repeat(2,1fr);
  gap:28px;max-width:1100px;margin-top:52px;
}
.testi{
  display:flex;gap:24px;
  padding:36px;background:var(--cream);
  border-radius:10px;
  transition:box-shadow .3s;
}
.testi:hover{box-shadow:0 12px 40px rgba(0,0,0,.07)}
.testi-img{
  width:80px;height:80px;border-radius:50%;
  object-fit:cover;flex-shrink:0;
  border:3px solid #fff;box-shadow:0 4px 14px rgba(0,0,0,.12);
}
.testi-body{flex:1}
.testi-stars{font-size:.8rem;color:#f4b400;letter-spacing:2px;margin-bottom:10px}
.testi-q{
  font-family:var(--serif);font-size:1.05rem;font-style:italic;
  line-height:1.6;color:var(--ink);margin-bottom:18px;font-weight:400;
}
.testi-name{font-weight:600;font-size:.85rem}
.testi-detail{font-size:.75rem;color:#aaa;margin-top:2px}

/* ═══ LOCATION ═══ */
#location{background:var(--ink);overflow:hidden}
.loc-grid{display:grid;grid-template-columns:1fr 1fr}
.loc-info{
  padding:110px 8% 110px 6%;
  display:flex;flex-direction:column;justify-content:center;
}
.loc-info h2.s-title{color:#fff}
.loc-detail{display:flex;gap:16px;margin-bottom:28px}
.loc-icon{color:var(--red);font-size:1rem;margin-top:3px;flex-shrink:0}
.loc-lbl{font-size:.65rem;letter-spacing:.18em;text-transform:uppercase;color:rgba(255,255,255,.3);margin-bottom:4px}
.loc-val{font-size:.95rem;color:rgba(255,255,255,.75);line-height:1.5}
.loc-val a{color:rgba(255,255,255,.75);text-decoration:none}
.loc-val a:hover{color:#fff}
.loc-map{position:relative;height:100%}
.loc-map iframe{display:block;width:100%;height:100%;border:none;filter:grayscale(20%) contrast(1.05)}

/* ═══ CTA BAND ═══ */
#ctaband{
  background:var(--red);padding:90px 6%;
  text-align:center;position:relative;overflow:hidden;
}
#ctaband::before{
  content:'VONVATI';
  position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);
  font-family:var(--serif);font-size:16rem;font-weight:900;
  color:rgba(255,255,255,.04);white-space:nowrap;pointer-events:none;
  letter-spacing:.05em;
}
#ctaband h2{
  font-family:var(--serif);font-size:clamp(2rem,4.5vw,3.5rem);
  color:#fff;font-weight:700;margin-bottom:12px;position:relative;
}
#ctaband p{color:rgba(255,255,255,.72);margin-bottom:38px;font-size:1rem;position:relative}
.btn-white{
  background:#fff;color:var(--red);border:none;
  padding:18px 50px;border-radius:100px;
  font-size:.82rem;letter-spacing:.13em;text-transform:uppercase;
  font-weight:700;cursor:pointer;text-decoration:none;display:inline-block;
  position:relative;
  transition:transform .2s,box-shadow .25s;
  font-family:var(--sans);
}
.btn-white:hover{transform:translateY(-3px);box-shadow:0 16px 40px rgba(0,0,0,.25)}

/* ═══ FORM ═══ */
#form-sec{padding:110px 6%;background:var(--white)}
.form-wrap{
  display:grid;grid-template-columns:1fr 1fr;
  gap:80px;max-width:1100px;align-items:center;
}
.form-left p{font-size:.95rem;color:#666;line-height:1.8;max-width:400px;margin-bottom:32px}
.pay-badges{display:flex;gap:10px;flex-wrap:wrap}
.pay-b{
  background:var(--cream);border:1px solid #e5e2de;
  padding:8px 16px;border-radius:100px;
  font-size:.78rem;color:#666;display:flex;align-items:center;gap:6px;
}
.cform{display:flex;flex-direction:column;gap:18px}
.fg{display:flex;flex-direction:column;gap:6px}
.fg label{font-size:.68rem;letter-spacing:.15em;text-transform:uppercase;color:#aaa}
.fg input,.fg select{
  border:1px solid #e5e2de;border-radius:8px;
  padding:14px 18px;font-family:var(--sans);font-size:.9rem;
  color:var(--ink);background:#fff;outline:none;
  transition:border-color .25s,box-shadow .25s;
  -webkit-appearance:none;
}
.fg input:focus,.fg select:focus{
  border-color:var(--ink);
  box-shadow:0 0 0 3px rgba(13,13,13,.06);
}
.form-send{
  background:var(--ink);color:#fff;border:none;
  padding:16px;border-radius:100px;cursor:pointer;
  font-family:var(--sans);font-size:.8rem;letter-spacing:.13em;
  text-transform:uppercase;font-weight:600;margin-top:6px;
  transition:background .25s,transform .2s;
}
.form-send:hover{background:var(--red);transform:translateY(-1px)}

/* ═══ FOOTER ═══ */
footer{background:var(--ink);padding:70px 6% 36px;border-top:1px solid rgba(255,255,255,.06)}
.footer-g{
  display:grid;grid-template-columns:2fr 1fr 1fr;
  gap:60px;max-width:1200px;margin-bottom:52px;
}
.f-logo{
  font-family:var(--serif);font-size:1.7rem;font-weight:700;
  color:#fff;margin-bottom:14px;letter-spacing:.02em;
}
.f-logo span{color:var(--red)}
.f-tagline{font-size:.85rem;color:rgba(255,255,255,.3);max-width:280px;line-height:1.7}
.f-col h4{
  font-size:.65rem;letter-spacing:.2em;text-transform:uppercase;
  color:rgba(255,255,255,.3);margin-bottom:20px;
}
.f-links{list-style:none;display:flex;flex-direction:column;gap:10px}
.f-links a{
  color:rgba(255,255,255,.5);text-decoration:none;
  font-size:.87rem;transition:color .2s;
}
.f-links a:hover{color:#fff}
.footer-bot{
  border-top:1px solid rgba(255,255,255,.07);padding-top:28px;
  display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:16px;
}
.f-copy{font-size:.76rem;color:rgba(255,255,255,.2)}
.f-socials{display:flex;gap:12px}
.f-s{
  width:38px;height:38px;border-radius:50%;
  border:1px solid rgba(255,255,255,.12);
  display:flex;align-items:center;justify-content:center;
  color:rgba(255,255,255,.4);text-decoration:none;font-size:.75rem;font-weight:600;
  transition:border-color .25s,color .25s,background .25s;
}
.f-s:hover{border-color:var(--red);color:var(--red)}

/* ═══ WA FLOAT ═══ */
.wa-btn{
  position:fixed;bottom:28px;right:28px;z-index:300;
  background:#25d366;color:#fff;
  width:62px;height:62px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  text-decoration:none;
  box-shadow:0 6px 24px rgba(37,211,102,.45);
  animation:waPulse 2.5s infinite;
  transition:transform .2s;
}
.wa-btn:hover{transform:scale(1.1)}
@keyframes waPulse{
  0%,100%{box-shadow:0 6px 24px rgba(37,211,102,.45)}
  50%{box-shadow:0 6px 40px rgba(37,211,102,.7)}
}
.wa-tip{
  position:fixed;bottom:38px;right:100px;z-index:299;
  background:#fff;color:var(--ink);padding:10px 18px;border-radius:100px;
  font-size:.8rem;font-weight:500;box-shadow:0 4px 20px rgba(0,0,0,.12);
  white-space:nowrap;opacity:0;pointer-events:none;
  transform:translateX(10px);
  transition:opacity .3s,transform .3s;
}
.wa-btn:hover ~ .wa-tip,.wa-tip:hover{opacity:1;transform:translateX(0)}

/* ═══ RESPONSIVE ═══ */
@media(max-width:1100px){
  .classes-scroll{grid-template-columns:repeat(3,1fr)}
  .pricing-grid{grid-template-columns:repeat(2,1fr)}
  .exp-cards{grid-template-columns:1fr 1fr}
  .gallery-strip{grid-template-columns:repeat(3,1fr)}
  .gallery-strip .gs-img:nth-child(4),.gallery-strip .gs-img:nth-child(5){display:none}
  .testi-grid{grid-template-columns:1fr}
}
@media(max-width:900px){
  .nav-links{display:none}
  .hamburger{display:flex}
  .hero-right{display:none}
  .about-wrap,.form-wrap,.loc-grid,.footer-g{grid-template-columns:1fr}
  .about-img-grid{grid-template-rows:220px 180px}
  .classes-scroll{grid-template-columns:repeat(2,1fr)}
  .cls-kids{grid-column:span 2}
  .exp-cards{grid-template-columns:1fr}
  .exp-c{border-right:none;border-bottom:1px solid rgba(255,255,255,.07)}
  .loc-map{height:360px}
  .how-grid{grid-template-columns:1fr}
  .footer-g{gap:36px}
  nav{padding:16px 4%}
  section{padding:80px 4%}
  #about,#classes,#pricing,#how,#reviews,#testimonials,#form-sec{padding:80px 4%}
  #location .loc-info{padding:80px 4%}
}
@media(max-width:600px){
  h1.hero-h{font-size:3rem}
  .big-score{font-size:5rem}
  .pricing-grid{grid-template-columns:1fr}
  .classes-scroll{grid-template-columns:1fr 1fr}
  .gallery-strip{grid-template-columns:1fr 1fr}
  .gallery-strip .gs-img:nth-child(5){display:none}
  .testi{flex-direction:column}
  .testi-img{width:60px;height:60px}
  #ctaband::before{font-size:6rem}
}
</style>
</head>
<body>

<!-- NAV -->
<nav id="navbar">
  <a href="#" class="nav-logo">Vonvati<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#about">Nosotros</a></li>
    <li><a href="#classes">Clases</a></li>
    <li><a href="#pricing">Precios</a></li>
    <li><a href="#location">Ubicación</a></li>
    <li><a href="https://wa.me/523311964499?text=Quiero%20informes%20de%20las%20clases" target="_blank" class="nav-pill">Inscríbete</a></li>
  </ul>
  <div class="hamburger" id="hbg" onclick="toggleNav()">
    <span></span><span></span><span></span>
  </div>
</nav>

<div id="mob-menu">
  <a href="#about" onclick="closeNav()">Nosotros</a>
  <a href="#classes" onclick="closeNav()">Clases</a>
  <a href="#pricing" onclick="closeNav()">Precios</a>
  <a href="#location" onclick="closeNav()">Ubicación</a>
  <a href="https://wa.me/523311964499?text=Quiero%20informes%20de%20las%20clases" target="_blank" class="mob-cta" onclick="closeNav()">Inscríbete ahora</a>
</div>

<!-- HERO -->
<section id="hero">
  <div class="hero-img"></div>
  <div class="hero-overlay"></div>
  <div class="hero-body">
    <div class="hero-left">
      <div class="hero-tag">Guadalajara · Jalisco · México</div>
      <h1 class="hero-h">Aprende<br>a <em>bailar</em><br>desde cero.</h1>
      <p class="hero-sub">Una academia boutique donde el ritmo, la confianza y la comunidad se convierten en tu mejor versión.</p>
      <div class="hero-btns">
        <a href="https://wa.me/523311964499?text=Quiero%20inscribirme%20en%20Vonvati" target="_blank" class="btn-red">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
          Inscríbete ahora
        </a>
        <a href="#classes" class="btn-ghost">Ver clases →</a>
      </div>
    </div>
    <div class="hero-right">
      <div class="hero-stat">
        <div class="hero-stat-n">7<span>+</span></div>
        <div class="hero-stat-l">Estilos de baile</div>
      </div>
      <div class="hero-stat">
        <div class="hero-stat-n">5<span>★</span></div>
        <div class="hero-stat-l">Calificación Google</div>
      </div>
      <div class="hero-stat">
        <div class="hero-stat-n">GDL<span>.</span></div>
        <div class="hero-stat-l">Guadalajara, Jalisco</div>
      </div>
    </div>
  </div>
  <div class="hero-scroll">
    <div class="scroll-line"></div>
    Scroll
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-wrap">
    <div class="about-text rv">
      <div class="section-label">Sobre nosotros</div>
      <h2 class="s-title">Más que una<br><em>escuela de baile</em></h2>
      <div class="red-bar"></div>
      <p>Vonvati World Academy nació con una visión clara: crear un espacio donde cualquier persona, sin importar su experiencia previa, pueda descubrir el baile como herramienta de transformación personal.</p>
      <p>Somos una comunidad activa en Guadalajara con instructores apasionados, metodología probada y un ambiente que combina exigencia con diversión real.</p>
      <div class="about-pills">
        <div class="pill"><span class="pill-dot"></span>Instructores con experiencia nacional e internacional</div>
        <div class="pill"><span class="pill-dot"></span>Grupos pequeños para atención personalizada</div>
        <div class="pill"><span class="pill-dot"></span>Ambiente 100% libre de juicios, para todos los niveles</div>
        <div class="pill"><span class="pill-dot"></span>Eventos sociales y salidas de baile cada mes</div>
      </div>
    </div>
    <div class="about-img-grid rv d2">
      <div class="ab-img tall">
        <img src="https://images.unsplash.com/photo-1504609813442-a8924e83f76e?w=600&q=80&fit=crop&crop=center" alt="Clases de baile Vonvati" loading="lazy">
      </div>
      <div class="ab-img">
        <img src="https://images.unsplash.com/photo-1547153760-18fc86324498?w=600&q=80&fit=crop&crop=center" alt="Bachata Guadalajara" loading="lazy">
      </div>
      <div class="ab-img">
        <img src="https://images.unsplash.com/photo-1545959570-a94084071b5d?w=600&q=80&fit=crop&crop=center" alt="Ambiente Vonvati" loading="lazy">
      </div>
    </div>
  </div>
</section>

<!-- CLASSES -->
<section id="classes">
  <div class="classes-top rv">
    <div>
      <div class="section-label" style="color:var(--red)">Lo que enseñamos</div>
      <h2 class="s-title">Elige tu<br><em style="color:rgba(255,255,255,.5)">estilo favorito</em></h2>
    </div>
    <p>Desde la salsa más elegante hasta los ritmos más urbanos. Tenemos el estilo perfecto para ti, sin importar tu nivel.</p>
  </div>
  <div class="classes-scroll rv d1">

    <!-- SALSA — pareja bailando salsa latina vibrante -->
    <div class="cls-card">
      <img src="https://images.unsplash.com/photo-1504609813442-a8924e83f76e?w=700&h=900&q=85&fit=crop&crop=center" alt="Clases de Salsa Guadalajara" loading="lazy">
      <div class="cls-overlay"></div>
      <div class="cls-content">
        <span class="cls-tag">Principal</span>
        <div class="cls-name">Salsa</div>
        <div class="cls-desc">Ritmo, elegancia y sabor latino en cada paso. Nuestro estilo estrella.</div>
      </div>
    </div>

    <!-- BACHATA — pareja en posición de bachata sensual -->
    <div class="cls-card">
      <img src="https://images.unsplash.com/photo-1541701494587-cb58502866ab?w=700&h=900&q=85&fit=crop&crop=center" alt="Clases de Bachata Guadalajara" loading="lazy">
      <div class="cls-overlay"></div>
      <div class="cls-content">
        <div class="cls-name">Bachata</div>
        <div class="cls-desc">Sensual y expresiva. El baile de pareja más popular del mundo.</div>
      </div>
    </div>

    <!-- CUMBIA — baile grupal festivo y colorido -->
    <div class="cls-card">
      <img src="https://images.unsplash.com/photo-1533174072545-7a4b6ad7a6c3?w=700&h=900&q=85&fit=crop&crop=center" alt="Clases de Cumbia Guadalajara" loading="lazy">
      <div class="cls-overlay"></div>
      <div class="cls-content">
        <div class="cls-name">Cumbia</div>
        <div class="cls-desc">Raíces mexicanas, alegría pura. Aprende a bailar lo que todos bailan.</div>
      </div>
    </div>

    <!-- SALSA CUBANA — baile latino pareja -->
    <div class="cls-card">
      <img src="https://images.unsplash.com/photo-1519925610903-381054cc2a1c?w=700&h=900&q=85&fit=crop&crop=center" alt="Salsa Cubana Guadalajara" loading="lazy">
      <div class="cls-overlay"></div>
      <div class="cls-content">
        <div class="cls-name">Salsa Cubana</div>
        <div class="cls-desc">Círculos, casino y sabor caribeño. Baile social por excelencia.</div>
      </div>
    </div>

    <!-- HOUSE — bailarín urbano con energía callejera -->
    <div class="cls-card">
      <img src="https://images.unsplash.com/photo-1508700115892-45ecd05ae2ad?w=700&h=900&q=85&fit=crop&crop=center" alt="House Dance Guadalajara" loading="lazy">
      <div class="cls-overlay"></div>
      <div class="cls-content">
        <div class="cls-name">House</div>
        <div class="cls-desc">Estilo urbano con roots en Chicago. Groove, libertad y expresión.</div>
      </div>
    </div>

    <!-- HEELS — chicas en tacones bailando -->
    <div class="cls-card">
      <img src="https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=700&h=900&q=85&fit=crop&crop=center" alt="Heels Dance Guadalajara" loading="lazy">
      <div class="cls-overlay"></div>
      <div class="cls-content">
        <div class="cls-name">Heels</div>
        <div class="cls-desc">Empoderamiento femenino. Fuerza, sensualidad y actitud en cada movimiento.</div>
      </div>
    </div>

    <!-- SALSA KIDS — niños bailando latino -->
    <div class="cls-card cls-kids">
      <img src="https://images.unsplash.com/photo-1546483875-ad9014c88eba?w=1400&h=600&q=85&fit=crop&crop=center" alt="Salsa Kids Guadalajara" loading="lazy">
      <div class="cls-overlay"></div>
      <div class="cls-content">
        <span class="cls-tag">Niños</span>
        <div class="cls-name">Salsa Kids</div>
        <div class="cls-desc">Para los más pequeños. Lunes y miércoles 7:00 pm · $550 MXN/mes</div>
      </div>
    </div>

  </div>
</section>

<!-- PRICING -->
<section id="pricing">
  <div class="pricing-intro rv">
    <div class="section-label">Inversión</div>
    <h2 class="s-title">Planes que se<br><em>adaptan a ti</em></h2>
    <div class="red-bar"></div>
    <p>Sin contratos eternos ni letras chicas. Solo elige el plan que encaja con tu agenda y presupuesto.</p>
  </div>
  <div class="pricing-grid">

    <div class="p-card rv d1">
      <div class="p-label">Clase suelta</div>
      <div class="p-price"><sup>$</sup>150</div>
      <div class="p-period">por clase · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> Prueba sin compromiso</div>
        <div class="p-feat"><span class="ck">✓</span> Cualquier estilo disponible</div>
        <div class="p-feat"><span class="ck">✓</span> Ideal para conocernos</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%20una%20clase%20suelta" target="_blank" class="p-btn">Reservar clase</a>
    </div>

    <div class="p-card rv d2">
      <div class="p-label">Paquete 4 clases</div>
      <div class="p-price"><sup>$</sup>450</div>
      <div class="p-period">válido 2 meses · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> 4 clases a tu ritmo</div>
        <div class="p-feat"><span class="ck">✓</span> Válidas por 2 meses</div>
        <div class="p-feat"><span class="ck">✓</span> Agenda flexible</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%20el%20paquete%20de%204%20clases" target="_blank" class="p-btn">Elegir plan</a>
    </div>

    <div class="p-card rv d3">
      <div class="p-label">Paquete 8 clases</div>
      <div class="p-price"><sup>$</sup>600</div>
      <div class="p-period">válido 2 meses · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> 8 clases, más ahorro</div>
        <div class="p-feat"><span class="ck">✓</span> Válidas por 2 meses</div>
        <div class="p-feat"><span class="ck">✓</span> Solo $75 por clase</div>
        <div class="p-feat"><span class="ck">✓</span> Ideal para ir 2 veces/semana</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%20el%20paquete%20de%208%20clases" target="_blank" class="p-btn">Elegir plan</a>
    </div>

    <div class="p-card rv d3">
      <div class="p-label">1 Curso mensual</div>
      <div class="p-price"><sup>$</sup>600</div>
      <div class="p-period">al mes · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> Todas las clases del mes</div>
        <div class="p-feat"><span class="ck">✓</span> Un género a elegir</div>
        <div class="p-feat"><span class="ck">✓</span> Múltiples horarios</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%201%20curso%20mensual" target="_blank" class="p-btn">Elegir plan</a>
    </div>

    <!-- FEATURED -->
    <div class="p-card hot rv d1">
      <div class="hot-tag">Más popular</div>
      <div class="p-label">2 Cursos mensuales</div>
      <div class="p-price"><sup>$</sup>1,000</div>
      <div class="p-period">al mes · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> 2 estilos de baile</div>
        <div class="p-feat"><span class="ck">✓</span> Ahorra $200 vs individual</div>
        <div class="p-feat"><span class="ck">✓</span> Todas las clases del mes</div>
        <div class="p-feat"><span class="ck">✓</span> Progreso doble garantizado</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%20los%202%20cursos%20por%20%241%2C000" target="_blank" class="p-btn">¡Quiero este plan!</a>
    </div>

    <div class="p-card rv d2">
      <div class="p-label">3 Cursos mensuales</div>
      <div class="p-price"><sup>$</sup>1,350</div>
      <div class="p-period">al mes · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> 3 estilos diferentes</div>
        <div class="p-feat"><span class="ck">✓</span> Ahorra $450 vs individual</div>
        <div class="p-feat"><span class="ck">✓</span> Máximo desarrollo</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%203%20cursos%20mensuales" target="_blank" class="p-btn">Elegir plan</a>
    </div>

    <div class="p-card rv d3">
      <div class="p-label">En pareja</div>
      <div class="p-price"><sup>$</sup>1,100</div>
      <div class="p-period">por pareja · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> 2 personas, 1 pago</div>
        <div class="p-feat"><span class="ck">✓</span> Mismo curso juntos</div>
        <div class="p-feat"><span class="ck">✓</span> Experiencia romántica</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%20el%20plan%20en%20pareja" target="_blank" class="p-btn">Elegir plan</a>
    </div>

    <div class="p-card rv d1">
      <div class="p-label">Grupo de 3</div>
      <div class="p-price"><sup>$</sup>1,350</div>
      <div class="p-period">por grupo · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> 3 amigos, 1 precio</div>
        <div class="p-feat"><span class="ck">✓</span> Aprenden juntos</div>
        <div class="p-feat"><span class="ck">✓</span> Experiencia social completa</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%20el%20plan%20para%20grupo%20de%203" target="_blank" class="p-btn">Elegir plan</a>
    </div>

    <div class="p-card rv d2">
      <div class="p-label">Salsa Kids</div>
      <div class="p-price"><sup>$</sup>550</div>
      <div class="p-period">al mes · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> Lun y mié 7:00 pm</div>
        <div class="p-feat"><span class="ck">✓</span> Grupos pequeños</div>
        <div class="p-feat"><span class="ck">✓</span> Maestros especializados</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%20informes%20de%20Salsa%20Kids" target="_blank" class="p-btn">Inscribir a mi hijo</a>
    </div>

    <div class="p-card rv d3" style="border-top:3px solid var(--red)">
      <div class="p-label">Anualidad</div>
      <div class="p-price"><sup>$</sup>6,000</div>
      <div class="p-period">por año, por género · MXN</div>
      <div class="p-line"></div>
      <div class="p-feats">
        <div class="p-feat"><span class="ck">✓</span> Solo $500/mes efectivo</div>
        <div class="p-feat"><span class="ck">✓</span> El mejor precio anual</div>
        <div class="p-feat"><span class="ck">✓</span> Prioridad en eventos</div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%20informes%20de%20la%20anualidad" target="_blank" class="p-btn">Consultar anualidad</a>
    </div>

  </div>
  <p class="pricing-note rv">Todos los precios incluyen acceso a clases del género seleccionado. Los paquetes son válidos por 2 meses. Puedes asistir en diferentes horarios dentro del mismo mes. Métodos de pago: <strong>Efectivo · Transferencia · Tarjeta</strong></p>
</section>

<!-- HOW IT WORKS -->
<section id="how">
  <div class="section-label rv">Sin complicaciones</div>
  <h2 class="s-title rv">Mensualidad <em>vs</em> Paquetes</h2>
  <div class="red-bar rv"></div>
  <div class="how-grid rv d1">
    <div class="how-card">
      <div class="how-num">01</div>
      <div class="how-title">Mensualidad — Para comprometidos</div>
      <p class="how-body">Pago mensual fijo. Incluye <strong>todas las clases del mes</strong> del mismo género. Puedes asistir en diferentes horarios según tu disponibilidad.</p>
      <div class="how-items">
        <div class="how-item">Ideal para progresar de forma constante</div>
        <div class="how-item">Máximo aprovechamiento por precio</div>
        <div class="how-item">Acceso a todos los horarios del género elegido</div>
        <div class="how-item">Desde $600 MXN al mes</div>
      </div>
    </div>
    <div class="how-card">
      <div class="how-num">02</div>
      <div class="how-title">Paquetes — Para agendas variables</div>
      <p class="how-body">Opciones de <strong>4 u 8 clases</strong> que puedes usar en un periodo de hasta 2 meses. No pierdes clases si tu agenda cambia.</p>
      <div class="how-items">
        <div class="how-item">Perfecto si tienes poco tiempo libre</div>
        <div class="how-item">Clases válidas por 2 meses</div>
        <div class="how-item">Sin presión de asistir cada semana</div>
        <div class="how-item">Desde $450 MXN por 4 clases</div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience" style="padding:0">
  <div class="exp-banner">
    <div class="exp-banner-ov"></div>
    <div class="exp-banner-content rv">
      <div class="section-label">Por qué elegirnos</div>
      <h2 class="s-title">Una experiencia<br><em style="color:rgba(255,255,255,.5)">que va más allá</em></h2>
      <p>No solo enseñamos pasos. Creamos una comunidad donde la música, los amigos y la confianza se convierten en parte de tu vida.</p>
      <a href="https://wa.me/523311964499?text=Quiero%20informes%20de%20las%20clases" target="_blank" class="btn-red">Conocer más →</a>
    </div>
  </div>
  <div class="exp-cards">
    <div class="exp-c rv">
      <div class="exp-icon">🎓</div>
      <div class="exp-name">Aprendizaje real</div>
      <p class="exp-desc">Metodología progresiva desde el primer paso hasta técnicas avanzadas. Instructores que adaptan la enseñanza a cada alumno.</p>
    </div>
    <div class="exp-c rv d1">
      <div class="exp-icon">🤝</div>
      <div class="exp-name">Comunidad activa</div>
      <p class="exp-desc">Eres parte de algo más grande. Eventos, convivios y salidas que hacen del baile una experiencia social completa y memorable.</p>
    </div>
    <div class="exp-c rv d2">
      <div class="exp-icon">💪</div>
      <div class="exp-name">Confianza garantizada</div>
      <p class="exp-desc">Cientos de alumnos llegaron sin experiencia. Hoy bailan con seguridad. Ambiente libre de juicios, para todos los niveles.</p>
    </div>
    <div class="exp-c rv d3">
      <div class="exp-icon">🎉</div>
      <div class="exp-name">Eventos y salidas</div>
      <p class="exp-desc">Noches de baile, competencias y eventos especiales para poner en práctica lo aprendido en la vida real.</p>
    </div>
    <div class="exp-c rv d4">
      <div class="exp-icon">🕐</div>
      <div class="exp-name">Horarios flexibles</div>
      <p class="exp-desc">Múltiples horarios entre semana y fines de semana. Siempre hay uno que se adapta a tu vida.</p>
    </div>
    <div class="exp-c rv d3">
      <div class="exp-icon">📍</div>
      <div class="exp-name">Ubicación céntrica</div>
      <p class="exp-desc">Belisario Domínguez 1911, Guadalajara. Fácil de llegar desde cualquier zona de la ciudad.</p>
    </div>
  </div>
</section>

<!-- GALLERY STRIP -->
<div class="gallery-strip">
  <div class="gs-img"><img src="https://images.unsplash.com/photo-1504609813442-a8924e83f76e?w=500&h=300&q=80&fit=crop&crop=center" alt="Salsa" loading="lazy"></div>
  <div class="gs-img"><img src="https://images.unsplash.com/photo-1541701494587-cb58502866ab?w=500&h=300&q=80&fit=crop&crop=center" alt="Bachata" loading="lazy"></div>
  <div class="gs-img"><img src="https://images.unsplash.com/photo-1533174072545-7a4b6ad7a6c3?w=500&h=300&q=80&fit=crop&crop=center" alt="Cumbia" loading="lazy"></div>
  <div class="gs-img"><img src="https://images.unsplash.com/photo-1508700115892-45ecd05ae2ad?w=500&h=300&q=80&fit=crop&crop=center" alt="House" loading="lazy"></div>
  <div class="gs-img"><img src="https://images.unsplash.com/photo-1518611012118-696072aa579a?w=500&h=300&q=80&fit=crop&crop=top" alt="Heels" loading="lazy"></div>
</div>

<!-- REVIEWS -->
<section id="reviews">
  <div class="reviews-top rv">
    <div class="big-score">5.0</div>
    <div class="reviews-meta-col">
      <div class="stars-row">★★★★★</div>
      <p>Calificación en Google Maps · Reseñas verificadas</p>
    </div>
  </div>
  <div class="reviews-grid">

    <div class="rv-card rv d1">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Tavo">
        <div><div class="rv-name">Tavo</div><div class="rv-date">hace 3 días</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Increíble academia. Los maestros te hacen sentir cómodo desde el primer día. Ya llevo 2 meses y el cambio en mi forma de bailar es notorio. Totalmente recomendado.</p>
    </div>

    <div class="rv-card rv d2">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Hugo">
        <div><div class="rv-name">Hugo</div><div class="rv-date">hace 1 semana</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Fui sin saber absolutamente nada de baile y ahora ya voy a eventos de salsa. Los precios son muy accesibles y la enseñanza de verdad se nota. 10/10.</p>
    </div>

    <div class="rv-card rv d3">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Angie">
        <div><div class="rv-name">Angie</div><div class="rv-date">hace 2 semanas</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Lo mejor que hice fue inscribirme aquí. Aprendí salsa y bachata al mismo tiempo. La comunidad es increíble y los convivios mensuales son lo mejor.</p>
    </div>

    <div class="rv-card rv d4">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1489424731084-a5d8b219a5bb?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Marlene">
        <div><div class="rv-name">Marlene</div><div class="rv-date">hace 3 semanas</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Vine con mi novio y fue la mejor decisión. Aprendimos salsa juntos, los maestros son súper pacientes y el ambiente es muy agradable. Ya somos parte de la comunidad.</p>
    </div>

    <div class="rv-card rv d1">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Cruz">
        <div><div class="rv-name">Cruz</div><div class="rv-date">hace 1 mes</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">El nivel de los instructores es impresionante. No solo enseñan pasos, te enseñan musicalidad y conexión con la música. Una academia seria y profesional.</p>
    </div>

    <div class="rv-card rv d2">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Isra">
        <div><div class="rv-name">Isra</div><div class="rv-date">hace 1 mes</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Tomé el paquete de 8 clases primero para probar y me encantó tanto que ya me inscribí en mensualidad. Vale cada peso, el ambiente es de 10.</p>
    </div>

    <div class="rv-card rv d3">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Miriam">
        <div><div class="rv-name">Miriam</div><div class="rv-date">hace 5 días</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Empecé con heels y me cambió la vida. La maestra es increíble y te da confianza en cada clase. Ahora también tomo salsa y no me arrepiento para nada.</p>
    </div>

    <div class="rv-card rv d4">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Fer">
        <div><div class="rv-name">Fer</div><div class="rv-date">hace 2 semanas</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Súper contenta con Vonvati. Llevo 4 meses y ya bailo en eventos sociales con seguridad total. Antes ni siquiera salía a la pista. El cambio es real.</p>
    </div>

    <div class="rv-card rv d1">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1531746020798-e6953c6e8e04?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Marbella">
        <div><div class="rv-name">Marbella</div><div class="rv-date">hace 4 días</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Los horarios son muy flexibles y eso me ayudó mucho. Puedo ir en el horario que me acomoda cada semana. Excelente opción para personas con trabajo de tiempo completo.</p>
    </div>

    <div class="rv-card rv d2">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Jenny">
        <div><div class="rv-name">Jenny</div><div class="rv-date">hace 6 días</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Inscribí a mis hijos en Salsa Kids y están felices. El maestro los trata increíble y ya empiezan a soltarse y disfrutar la música. Muy recomendada para niños.</p>
    </div>

    <div class="rv-card rv d3">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1529626455594-4ff0802cfb7e?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Fabby">
        <div><div class="rv-name">Fabby</div><div class="rv-date">hace 2 semanas</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">El plan de 2 cursos es lo mejor que existe. Tomo bachata y cumbia y el precio es muy accesible. Los maestros son apasionados y eso se contagia.</p>
    </div>

    <div class="rv-card rv d4">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1508214751196-bcfd4ca60f91?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Cecy">
        <div><div class="rv-name">Cecy</div><div class="rv-date">hace 3 semanas</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Definitivamente el mejor lugar para aprender a bailar en Guadalajara. Ambiente profesional pero con mucha calidez humana. Ya les recomendé a todos mis amigos.</p>
    </div>

    <div class="rv-card rv d1">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1552058544-f2b08422138a?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Alex">
        <div><div class="rv-name">Alex</div><div class="rv-date">hace 1 semana</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Vine a probar con una clase suelta y ya no me fui. La metodología es muy clara y en pocas clases ya se notan los resultados. Los eventos sociales son increíbles.</p>
    </div>

    <div class="rv-card rv d2">
      <div class="rv-head">
        <img src="https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?w=80&h=80&q=80&fit=crop&crop=face" class="rv-av" style="object-fit:cover;border-radius:50%;width:44px;height:44px;" alt="Emmanuel">
        <div><div class="rv-name">Emmanuel</div><div class="rv-date">hace 5 días</div></div>
      </div>
      <div class="rv-stars">★★★★★</div>
      <p class="rv-text">Llevo 6 meses en salsa cubana y cada clase aprendo algo nuevo. Los maestros saben muchísimo y se nota el amor que le tienen a lo que hacen. Lugar único en GDL.</p>
    </div>

  </div>
</section>

<!-- TESTIMONIALS -->
<section id="testimonials">
  <div class="section-label rv">Historias reales</div>
  <h2 class="s-title rv">Lo que dicen<br><em>nuestros alumnos</em></h2>
  <div class="testi-grid">
    <div class="testi rv d1">
      <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=160&q=80&fit=crop&crop=face" alt="Sofía" class="testi-img" loading="lazy">
      <div class="testi-body">
        <div class="testi-stars">★★★★★</div>
        <p class="testi-q">"Llegué sin saber ni moverme al ritmo de la música. Hoy, tres meses después, bailo en eventos, hice amigos increíbles y me siento completamente diferente cuando entro a una fiesta."</p>
        <div class="testi-name">Angie</div>
        <div class="testi-detail">Salsa y Bachata · 3 meses en Vonvati</div>
      </div>
    </div>
    <div class="testi rv d2">
      <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=160&q=80&fit=crop&crop=face" alt="Rodrigo" class="testi-img" loading="lazy">
      <div class="testi-body">
        <div class="testi-stars">★★★★★</div>
        <p class="testi-q">"Vine porque un amigo me convenció. Pensé que el baile no era para mí. Ahora no falta ningún martes. La comunidad que se forma aquí es algo que no esperaba y que ya no cambiaría."</p>
        <div class="testi-name">Hugo</div>
        <div class="testi-detail">Salsa Cubana · 6 meses en Vonvati</div>
      </div>
    </div>
    <div class="testi rv d3">
      <img src="https://images.unsplash.com/photo-1489424731084-a5d8b219a5bb?w=160&q=80&fit=crop&crop=face" alt="Valeria" class="testi-img" loading="lazy">
      <div class="testi-body">
        <div class="testi-stars">★★★★★</div>
        <p class="testi-q">"Inscribí a mi hija en Salsa Kids y el cambio fue inmediato. Más confiada, más coordinada y siempre quiere ir. Los maestros son excelentes con los niños, muy recomendada."</p>
        <div class="testi-name">Jenny</div>
        <div class="testi-detail">Mamá · Salsa Kids · 2 meses</div>
      </div>
    </div>
    <div class="testi rv d4">
      <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?w=160&q=80&fit=crop&crop=face" alt="Daniela" class="testi-img" loading="lazy">
      <div class="testi-body">
        <div class="testi-stars">★★★★★</div>
        <p class="testi-q">"El plan de 2 cursos es lo mejor. Tomo salsa y heels en la misma semana. Me ha dado una seguridad en mí misma que no tenía. Literalmente cambió mi forma de caminar y de sentirme."</p>
        <div class="testi-name">Miriam</div>
        <div class="testi-detail">Salsa y Heels · 5 meses en Vonvati</div>
      </div>
    </div>
  </div>
</section>

<!-- LOCATION -->
<section id="location" style="padding:0">
  <div class="loc-grid">
    <div class="loc-info">
      <div class="section-label">Encuéntranos</div>
      <h2 class="s-title">Ubícanos en<br><em>Guadalajara</em></h2>
      <div style="width:44px;height:3px;background:var(--red);margin:24px 0 36px"></div>
      <div class="loc-detail">
        <span class="loc-icon">📍</span>
        <div>
          <div class="loc-lbl">Dirección</div>
          <div class="loc-val">Belisario Domínguez 1911<br>Col. Monumental<br>Guadalajara, Jalisco, México</div>
        </div>
      </div>
      <div class="loc-detail">
        <span class="loc-icon">📞</span>
        <div>
          <div class="loc-lbl">Teléfono</div>
          <div class="loc-val"><a href="tel:+523311964499">33 1196 4499</a></div>
        </div>
      </div>
      <div class="loc-detail">
        <span class="loc-icon">📸</span>
        <div>
          <div class="loc-lbl">Instagram</div>
          <div class="loc-val"><a href="https://instagram.com/vonvati" target="_blank">@vonvati</a></div>
        </div>
      </div>
      <div class="loc-detail">
        <span class="loc-icon">💳</span>
        <div>
          <div class="loc-lbl">Métodos de pago</div>
          <div class="loc-val">Efectivo · Transferencia · Tarjeta</div>
        </div>
      </div>
      <a href="https://wa.me/523311964499?text=Quiero%20informes%20de%20las%20clases" target="_blank" class="btn-red" style="margin-top:8px;align-self:flex-start">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
        Escríbenos por WhatsApp
      </a>
    </div>
    <div class="loc-map" style="min-height:520px">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3733.1!2d-103.349!3d20.660!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zVm9udmF0aSBXb3JsZCBBY2FkZW15!5e0!3m2!1ses!2smx!4v1&q=Belisario+Dom%C3%ADnguez+1911,+Guadalajara,+Jalisco"
        allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </div>
  </div>
</section>

<!-- CTA -->
<section id="ctaband">
  <h2>¿Listo para dar<br>el primer paso?</h2>
  <p>Únete hoy. Sin experiencia previa. Sin excusas.</p>
  <a href="https://wa.me/523311964499?text=Quiero%20inscribirme%20en%20Vonvati" target="_blank" class="btn-white">Únete hoy por WhatsApp →</a>
</section>

<!-- FORM -->
<section id="form-sec">
  <div class="form-wrap">
    <div class="form-left rv">
      <div class="section-label">Contáctanos</div>
      <h2 class="s-title">¿Tienes dudas?<br><em>Escríbenos</em></h2>
      <div class="red-bar"></div>
      <p>Déjanos tu información y uno de nuestros asesores te contactará por WhatsApp para orientarte sobre el plan ideal para ti, sin compromiso.</p>
      <div class="pay-badges">
        <div class="pay-b">💵 Efectivo</div>
        <div class="pay-b">🏦 Transferencia</div>
        <div class="pay-b">💳 Tarjeta</div>
      </div>
    </div>
    <div class="rv d2">
      <div class="cform">
        <div class="fg">
          <label for="fname">Nombre completo</label>
          <input type="text" id="fname" placeholder="Tu nombre completo">
        </div>
        <div class="fg">
          <label for="fwa">WhatsApp</label>
          <input type="tel" id="fwa" placeholder="33 XXXX XXXX">
        </div>
        <div class="fg">
          <label for="flvl">Nivel de experiencia</label>
          <select id="flvl">
            <option value="">Selecciona tu nivel</option>
            <option>Principiante — No sé bailar nada</option>
            <option>Básico — Sé algunos pasos</option>
            <option>Intermedio — Bailo en fiestas</option>
            <option>Avanzado — Quiero mejorar mi técnica</option>
          </select>
        </div>
        <div class="fg">
          <label for="fint">Estilo de interés</label>
          <select id="fint">
            <option value="">¿Qué quieres aprender?</option>
            <option>Salsa</option>
            <option>Bachata</option>
            <option>Cumbia</option>
            <option>Salsa Cubana</option>
            <option>House</option>
            <option>Heels</option>
            <option>Salsa Kids</option>
            <option>Varios estilos</option>
          </select>
        </div>
        <button class="form-send" onclick="enviarForm()">Enviar por WhatsApp →</button>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-g">
    <div>
      <div class="f-logo">Vonvati<span>.</span></div>
      <p class="f-tagline">Escuela de baile boutique en Guadalajara. Donde el ritmo transforma vidas desde el primer paso.</p>
    </div>
    <div class="f-col">
      <h4>Clases</h4>
      <ul class="f-links">
        <li><a href="#classes">Salsa</a></li>
        <li><a href="#classes">Bachata</a></li>
        <li><a href="#classes">Cumbia</a></li>
        <li><a href="#classes">Salsa Cubana</a></li>
        <li><a href="#classes">House · Heels</a></li>
        <li><a href="#classes">Salsa Kids</a></li>
      </ul>
    </div>
    <div class="f-col">
      <h4>Contacto</h4>
      <ul class="f-links">
        <li><a href="tel:+523311964499">33 1196 4499</a></li>
        <li><a href="https://instagram.com/vonvati" target="_blank">@vonvati</a></li>
        <li><a href="https://wa.me/523311964499?text=Quiero%20informes%20de%20las%20clases" target="_blank">WhatsApp</a></li>
        <li><a href="#location">Belisario Domínguez 1911</a></li>
        <li><a href="#location">Col. Monumental, Guadalajara</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bot">
    <p class="f-copy">© 2025 Vonvati World Academy. Todos los derechos reservados.</p>
    <div class="f-socials">
      <a href="https://instagram.com/vonvati" target="_blank" class="f-s" title="Instagram">IG</a>
      <a href="https://wa.me/523311964499?text=Quiero%20informes%20de%20las%20clases" target="_blank" class="f-s" title="WhatsApp">WA</a>
      <a href="tel:+523311964499" class="f-s" title="Llamar">📞</a>
    </div>
  </div>
</footer>

<!-- WA FLOAT -->
<a href="https://wa.me/523311964499?text=Quiero%20informes%20de%20las%20clases" target="_blank" class="wa-btn" title="Escríbenos por WhatsApp">
  <svg width="30" height="30" viewBox="0 0 24 24" fill="currentColor">
    <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
  </svg>
</a>
<div class="wa-tip">¡Escríbenos ahora!</div>

<script>
// NAV SCROLL
const nb=document.getElementById('navbar');
window.addEventListener('scroll',()=>{
  nb.classList.toggle('scrolled',window.scrollY>60);
});

// HAMBURGER
function toggleNav(){
  const m=document.getElementById('mob-menu');
  const h=document.getElementById('hbg');
  const open=m.style.display==='flex';
  m.style.display=open?'none':'flex';
  h.classList.toggle('open',!open);
}
function closeNav(){
  document.getElementById('mob-menu').style.display='none';
  document.getElementById('hbg').classList.remove('open');
}

// REVEAL ON SCROLL
const rvEls=document.querySelectorAll('.rv');
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){e.target.classList.add('in');obs.unobserve(e.target)}
  });
},{threshold:.1,rootMargin:'0px 0px -40px 0px'});
rvEls.forEach(el=>obs.observe(el));

// FORM → WHATSAPP
function enviarForm(){
  const name=document.getElementById('fname').value.trim();
  const wa=document.getElementById('fwa').value.trim();
  const lvl=document.getElementById('flvl').value;
  const int=document.getElementById('fint').value;
  if(!name||!wa){alert('Por favor ingresa tu nombre y WhatsApp.');return;}
  const msg=encodeURIComponent(`Hola! Me llamo ${name}. Quiero informes de las clases en Vonvati.\nNivel: ${lvl||'No especificado'}\nInterés: ${int||'No especificado'}\nMi WhatsApp: ${wa}`);
  window.open(`https://wa.me/523311964499?text=${msg}`,'_blank');
}
</script>
</body>

