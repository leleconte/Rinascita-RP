
:root{
  --gold:rgba(215,167,45,1);
  --gold-2:rgba(242,199,92,1);
  --wine:rgba(139,16,20,1);
  --wine-2:rgba(179,27,34,1);
  --ivory:rgba(255,248,232,1);
  --ink:rgba(10,6,8,1);
  --panel:rgba(20,10,13,.90);
  --panel-2:rgba(43,16,22,.84);
  --line:rgba(215,167,45,.24);
  --muted:rgba(255,241,199,.58);
}

*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

html,body{
  width:100%;
  height:100%;
  overflow:hidden;
  background:rgba(5,3,4,1);
  color:var(--ivory);
  font-family:Arial,Helvetica,sans-serif;
}

body{
  opacity:0;
  transition:opacity .34s ease, transform .34s ease;
}

body.page-ready{opacity:1}
body.page-leaving{opacity:0;transform:scale(.994)}

a{text-decoration:none;color:inherit}
button{font:inherit;color:inherit}

.site-shell{
  position:fixed;
  inset:0;
  overflow:hidden;
  background:
    linear-gradient(115deg,rgba(4,2,3,.90),rgba(13,6,9,.56) 48%,rgba(4,2,3,.91)),
    var(--page-bg,rgba(5,3,4,1));
  background-size:cover;
  background-position:center;
}

.site-shell::before{
  content:"";
  position:absolute;
  inset:0;
  pointer-events:none;
  background:
    radial-gradient(circle at 72% 18%,rgba(215,167,45,.11),transparent 26%),
    radial-gradient(circle at 18% 78%,rgba(139,16,20,.19),transparent 32%);
}

.site-shell::after{
  content:"";
  position:absolute;
  inset:0;
  pointer-events:none;
  opacity:.24;
  background-image:
    linear-gradient(rgba(255,255,255,.018) 1px,transparent 1px),
    linear-gradient(90deg,rgba(255,255,255,.018) 1px,transparent 1px);
  background-size:48px 48px;
}

.topbar{
  position:absolute;
  top:0;
  left:0;
  right:0;
  z-index:20;
  height:88px;
  display:grid;
  grid-template-columns:260px minmax(0,1fr) 230px;
  align-items:center;
  gap:20px;
  padding:0 42px;
  border-bottom:1px solid rgba(215,167,45,.13);
  background:rgba(10,5,7,.76);
}

.brand{
  display:flex;
  align-items:center;
  gap:12px;
}

.brand img{
  width:58px;
  height:58px;
  object-fit:contain;
  filter:drop-shadow(0 8px 18px rgba(0,0,0,.48));
}

.brand-copy{display:flex;flex-direction:column}
.brand-copy small{
  color:var(--gold-2);
  font-size:8px;
  font-weight:900;
  letter-spacing:1.9px;
}
.brand-copy strong{
  margin-top:5px;
  font-size:14px;
  letter-spacing:.5px;
}

.main-nav{
  display:flex;
  align-items:center;
  justify-content:center;
  gap:8px;
}

.nav-link{
  position:relative;
  min-width:112px;
  padding:14px 17px;
  border:1px solid transparent;
  border-radius:10px;
  color:rgba(255,248,232,.52);
  font-size:9px;
  font-weight:900;
  letter-spacing:.8px;
  text-align:center;
  transition:.22s ease;
}

.nav-link:hover,
.nav-link.active{
  color:var(--ivory);
  border-color:rgba(215,167,45,.22);
  background:rgba(139,16,20,.26);
  transform:translateY(-2px);
}

.nav-link.active::after{
  content:"";
  position:absolute;
  left:22%;
  right:22%;
  bottom:-1px;
  height:2px;
  background:var(--gold-2);
}

.top-actions{
  display:flex;
  justify-content:flex-end;
  gap:8px;
}

.pill{
  min-height:38px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  padding:0 15px;
  border:1px solid var(--line);
  border-radius:10px;
  background:rgba(34,13,18,.76);
  font-size:8px;
  font-weight:900;
  letter-spacing:.7px;
  transition:.2s ease;
}

.pill:hover{
  border-color:rgba(242,199,92,.66);
  background:rgba(139,16,20,.72);
  transform:translateY(-2px);
}

.is-disabled,
.is-disabled:hover{
  cursor:not-allowed;
  opacity:.55;
  transform:none;
  box-shadow:none;
}

.page{
  position:absolute;
  inset:88px 0 0;
  z-index:2;
  display:grid;
  grid-template-columns:minmax(0,1.2fr) minmax(420px,.8fr);
  align-items:center;
  gap:46px;
  padding:52px 68px 54px;
}

.page.single{
  grid-template-columns:1fr;
}

.hero-copy{
  max-width:760px;
  animation:heroIn .78s cubic-bezier(.16,.84,.28,1) both;
}

.eyebrow{
  display:flex;
  align-items:center;
  gap:10px;
  color:var(--gold-2);
  font-size:9px;
  font-weight:900;
  letter-spacing:2.5px;
}

.eyebrow::before{
  content:"";
  width:42px;
  height:2px;
  background:var(--gold);
}

.hero-copy h1{
  margin-top:18px;
  max-width:800px;
  font-family:Georgia,"Times New Roman",serif;
  font-size:clamp(56px,6vw,104px);
  line-height:.88;
  letter-spacing:-3px;
}

.hero-copy h1 span{
  display:block;
  color:var(--gold-2);
}

.hero-copy p{
  max-width:660px;
  margin-top:24px;
  color:rgba(255,248,232,.65);
  font-size:14px;
  line-height:1.72;
}

.hero-actions{
  display:flex;
  gap:10px;
  margin-top:30px;
}

.cta{
  min-height:50px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  gap:9px;
  padding:0 22px;
  border:1px solid rgba(215,167,45,.27);
  border-radius:11px;
  background:rgba(38,14,19,.82);
  font-size:9px;
  font-weight:900;
  letter-spacing:.9px;
  transition:.22s ease;
}

.cta.primary{
  border-color:rgba(242,199,92,.55);
  background:rgba(139,16,20,.90);
}

.cta:hover{
  transform:translateY(-3px);
  box-shadow:0 16px 32px rgba(0,0,0,.32);
}

.city-card{
  position:relative;
  min-height:520px;
  overflow:hidden;
  border:1px solid rgba(215,167,45,.22);
  border-radius:24px;
  background:rgba(20,10,13,.84);
  box-shadow:0 30px 80px rgba(0,0,0,.50);
  animation:cardIn .82s .10s cubic-bezier(.16,.84,.28,1) both;
}

.city-card::before{
  content:"";
  position:absolute;
  inset:0;
  background:
    linear-gradient(180deg,rgba(10,5,7,.10),rgba(10,5,7,.80)),
    var(--card-image) center/cover no-repeat;
  transform:scale(1.04);
  transition:transform 7s ease;
}

.city-card:hover::before{transform:scale(1.11)}

.city-card-content{
  position:absolute;
  inset:auto 0 0;
  z-index:2;
  padding:26px;
}

.city-card-content small{
  color:var(--gold-2);
  font-size:8px;
  font-weight:900;
  letter-spacing:1.6px;
}

.city-card-content h2{
  margin-top:7px;
  font-size:30px;
}

.city-card-content p{
  margin-top:9px;
  color:var(--muted);
  font-size:11px;
  line-height:1.55;
}

.status-row{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:8px;
  margin-top:18px;
}

.status{
  padding:13px;
  border:1px solid rgba(215,167,45,.15);
  border-radius:10px;
  background:rgba(20,10,13,.82);
}

.status b{display:block;color:var(--gold-2);font-size:16px}
.status span{display:block;margin-top:4px;color:var(--muted);font-size:7px}

.rome-line{
  position:absolute;
  left:0;
  right:0;
  bottom:-10px;
  z-index:1;
  height:250px;
  background:url("../img/rome_skyline.svg") center bottom/cover no-repeat;
  opacity:.54;
  pointer-events:none;
}

.page-index{
  position:absolute;
  right:38px;
  bottom:25px;
  z-index:10;
  color:rgba(255,248,232,.34);
  font-size:8px;
  font-weight:900;
  letter-spacing:1.4px;
}

.page-index b{color:var(--gold-2);font-size:16px}

.feature-stage{
  width:min(1280px,92vw);
  margin:0 auto;
}

.page-title{
  display:flex;
  align-items:end;
  justify-content:space-between;
  gap:24px;
  margin-bottom:25px;
}

.page-title div small{
  color:var(--gold-2);
  font-size:8px;
  font-weight:900;
  letter-spacing:1.8px;
}

.page-title h1{
  margin-top:8px;
  font-family:Georgia,"Times New Roman",serif;
  font-size:54px;
}

.page-title p{
  max-width:520px;
  color:var(--muted);
  font-size:11px;
  line-height:1.55;
  text-align:right;
}

.card-grid{
  display:grid;
  grid-template-columns:repeat(3,minmax(0,1fr));
  gap:12px;
}

.info-card{
  min-height:250px;
  display:flex;
  flex-direction:column;
  justify-content:space-between;
  padding:22px;
  border:1px solid rgba(215,167,45,.16);
  border-radius:16px;
  background:rgba(24,10,14,.88);
  transition:.24s ease;
  animation:tileIn .62s both;
}

.info-card:nth-child(2){animation-delay:.06s}
.info-card:nth-child(3){animation-delay:.12s}
.info-card:nth-child(4){animation-delay:.18s}
.info-card:nth-child(5){animation-delay:.24s}
.info-card:nth-child(6){animation-delay:.30s}

.info-card:hover{
  transform:translateY(-6px);
  border-color:rgba(242,199,92,.58);
  background:rgba(55,17,24,.92);
}

.info-card .number{
  color:rgba(242,199,92,.42);
  font-family:Georgia,"Times New Roman",serif;
  font-size:44px;
}

.info-card h3{
  font-size:17px;
}

.info-card p{
  margin-top:9px;
  color:var(--muted);
  font-size:10px;
  line-height:1.55;
}

.info-card footer{
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding-top:14px;
  border-top:1px solid rgba(215,167,45,.12);
  color:var(--gold-2);
  font-size:7px;
  font-weight:900;
  letter-spacing:.9px;
}

.rule-layout{
  display:grid;
  grid-template-columns:330px minmax(0,1fr);
  gap:16px;
  min-height:590px;
}

.rule-menu,
.rule-panel{
  border:1px solid rgba(215,167,45,.16);
  border-radius:17px;
  background:rgba(22,9,13,.90);
}

.rule-menu{padding:12px}

.rule-button{
  width:100%;
  min-height:60px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  margin-bottom:7px;
  padding:0 15px;
  border:1px solid rgba(215,167,45,.11);
  border-radius:10px;
  background:rgba(47,17,22,.62);
  cursor:pointer;
  font-size:9px;
  font-weight:900;
  text-align:left;
  transition:.2s ease;
}

.rule-button.active,
.rule-button:hover{
  border-color:rgba(242,199,92,.56);
  background:rgba(139,16,20,.72);
}

.rule-panel{
  position:relative;
  overflow:hidden;
  padding:34px;
}

.rule-content{
  position:absolute;
  inset:34px;
  opacity:0;
  transform:translateX(30px);
  pointer-events:none;
  transition:.32s ease;
}

.rule-content.active{
  opacity:1;
  transform:translateX(0);
  pointer-events:auto;
}

.rule-content small{
  color:var(--gold-2);
  font-size:8px;
  font-weight:900;
  letter-spacing:1.4px;
}

.rule-content h2{
  margin-top:9px;
  font-family:Georgia,"Times New Roman",serif;
  font-size:43px;
}

.rule-content p{
  margin-top:17px;
  color:var(--muted);
  font-size:12px;
  line-height:1.75;
}

.rule-points{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:9px;
  margin-top:24px;
}

.rule-point{
  padding:13px;
  border:1px solid rgba(215,167,45,.12);
  border-radius:9px;
  background:rgba(44,15,20,.65);
  color:rgba(255,248,232,.72);
  font-size:9px;
  line-height:1.45;
}

.join-grid{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:12px;
}

.join-card{
  min-height:330px;
  display:flex;
  flex-direction:column;
  padding:23px;
  border:1px solid rgba(215,167,45,.17);
  border-radius:17px;
  background:rgba(23,9,13,.90);
  transition:.22s ease;
}

.join-card:hover{
  transform:translateY(-6px);
  border-color:rgba(242,199,92,.58);
}

.join-card .step{
  color:var(--gold-2);
  font-family:Georgia,"Times New Roman",serif;
  font-size:50px;
}

.join-card h3{
  margin-top:12px;
  font-size:19px;
}

.join-card p{
  margin-top:12px;
  color:var(--muted);
  font-size:10px;
  line-height:1.55;
}

.join-card .cta{
  margin-top:auto;
  width:100%;
}

.footer-note{
  position:absolute;
  left:42px;
  bottom:20px;
  color:rgba(255,248,232,.28);
  font-size:7px;
  letter-spacing:.6px;
}

@keyframes heroIn{
  from{opacity:0;transform:translateX(-46px)}
  to{opacity:1;transform:translateX(0)}
}
@keyframes cardIn{
  from{opacity:0;transform:translateX(48px) scale(.97)}
  to{opacity:1;transform:translateX(0) scale(1)}
}
@keyframes tileIn{
  from{opacity:0;transform:translateY(28px)}
  to{opacity:1;transform:translateY(0)}
}

@media(max-width:1100px){
  .topbar{grid-template-columns:220px 1fr 150px;padding:0 20px}
  .nav-link{min-width:auto;padding:12px 10px}
  .page{padding:35px;gap:25px}
  .hero-copy h1{font-size:60px}
  .city-card{min-height:470px}
}


@media(max-width:900px){
  html,body{
    height:auto;
    min-height:100%;
    overflow-x:hidden;
    overflow-y:auto;
  }

  .site-shell{
    position:relative;
    inset:auto;
    min-height:100dvh;
    overflow:hidden;
  }

  .topbar{
    position:relative;
    height:auto;
    min-height:76px;
    display:flex;
    flex-wrap:wrap;
    gap:10px;
    padding:10px 16px 12px;
  }

  .brand img{
    width:48px;
    height:48px;
  }

  .top-actions{
    margin-left:auto;
  }

  .main-nav{
    order:3;
    width:100%;
    justify-content:flex-start;
    overflow-x:auto;
    padding-bottom:2px;
    scrollbar-width:thin;
  }

  .nav-link{
    flex:0 0 auto;
    min-width:max-content;
    padding:11px 13px;
  }

  .page,
  .page.single{
    position:relative;
    inset:auto;
    display:block;
    padding:38px 22px 76px;
  }

  .hero-copy{
    max-width:none;
  }

  .hero-copy h1{
    font-size:clamp(48px,13vw,76px);
    letter-spacing:-2px;
  }

  .city-card{
    min-height:430px;
    margin-top:34px;
  }

  .feature-stage{
    width:100%;
  }

  .page-title{
    display:block;
  }

  .page-title h1{
    font-size:clamp(38px,10vw,54px);
  }

  .page-title p{
    max-width:680px;
    margin-top:14px;
    text-align:left;
  }

  .card-grid,
  .join-grid{
    grid-template-columns:repeat(2,minmax(0,1fr));
  }

  .rule-layout{
    grid-template-columns:1fr;
    min-height:auto;
  }

  .rule-menu{
    display:grid;
    grid-template-columns:repeat(2,minmax(0,1fr));
    gap:7px;
  }

  .rule-button{
    margin-bottom:0;
  }

  .rule-panel{
    min-height:540px;
  }

  .page-index{
    right:20px;
    bottom:20px;
  }

  .footer-note{
    left:20px;
    bottom:22px;
  }

  .rome-line{
    opacity:.30;
  }
}

@media(max-width:620px){
  .brand-copy strong{
    font-size:11px;
  }

  .brand-copy small{
    font-size:7px;
  }

  .top-actions .pill:last-child{
    display:none;
  }

  .pill{
    min-height:34px;
    padding:0 12px;
  }

  .page,
  .page.single{
    padding:30px 16px 82px;
  }

  .hero-copy p{
    font-size:13px;
  }

  .hero-actions{
    flex-direction:column;
  }

  .hero-actions .cta{
    width:100%;
  }

  .city-card{
    min-height:390px;
    border-radius:18px;
  }

  .status-row,
  .card-grid,
  .join-grid,
  .rule-points,
  .rule-menu{
    grid-template-columns:1fr;
  }

  .info-card,
  .join-card{
    min-height:230px;
  }

  .rule-panel{
    min-height:620px;
    padding:22px;
  }

  .rule-content{
    inset:22px;
  }

  .rule-content h2{
    font-size:34px;
  }

  .footer-note{
    max-width:70%;
  }
}

@media(max-height:760px) and (min-width:901px){
  .page{
    padding-top:28px;
    padding-bottom:34px;
  }

  .city-card{
    min-height:420px;
  }

  .info-card{
    min-height:205px;
  }

  .rule-layout{
    min-height:500px;
  }
}

@media(prefers-reduced-motion:reduce){
  *,*::before,*::after{
    scroll-behavior:auto!important;
    animation-duration:.01ms!important;
    animation-iteration-count:1!important;
    transition-duration:.01ms!important;
  }
}
