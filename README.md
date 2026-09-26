<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Rotaract Club of Dhaka Abani</title>
<style>
  :root{
    --maroon:#7d1738;
    --maroon-deep:#5c0f28;
    --rose:#c23262;
    --pink-pale:#fbeef3;
    --pink-line:#eccbd8;
    --ink:#2a1620;
    --paper:#fffdfd;
    box-sizing:border-box;
    padding-top:env(safe-area-inset-top,0px);
    padding-bottom:env(safe-area-inset-bottom,0px);
  }
  *{box-sizing:border-box;}
  html{scroll-padding-top:78px;}
  html,body{height:100%;}
  body{
    margin:0;
    background:var(--paper);
    color:var(--ink);
    font-family:"Times New Roman", Times, Georgia, serif;
    -webkit-font-smoothing:antialiased;
  }
  a{color:inherit;}
  img{max-width:100%;display:block;}

  header.nav{
    position:sticky;top:0;top:env(safe-area-inset-top,0px);
    z-index:50;
    background:rgba(255,253,253,.94);
    border-bottom:1px solid var(--pink-line);
    backdrop-filter:blur(6px);
  }
  .nav-inner{
    max-width:1080px;margin:0 auto;
    display:flex;align-items:center;justify-content:space-between;
    padding:10px 20px;
    gap:16px;
  }
  .brand{display:flex;align-items:center;gap:10px;cursor:pointer;}
  .brand img{height:38px;width:auto;}
  .brand span{font-size:15px;letter-spacing:.02em;color:var(--maroon-deep);display:none;}
  nav.links{display:flex;gap:2px;flex-wrap:wrap;justify-content:flex-end;}
  nav.links button{
    font-family:inherit;font-size:15px;background:none;border:none;
    color:var(--ink);padding:10px 12px;cursor:pointer;
    border-bottom:2px solid transparent;
    transition:color .15s, border-color .15s;
  }
  nav.links button:hover{color:var(--maroon);}
  nav.links button.active{color:var(--maroon);border-bottom-color:var(--rose);}

  .page{display:none;animation:fade .35s ease;}
  .page.active{display:block;}
  @keyframes fade{from{opacity:0;transform:translateY(6px);}to{opacity:1;transform:translateY(0);}}

  .wrap{max-width:1080px;margin:0 auto;padding:0 20px;}
  .narrow{max-width:760px;margin:0 auto;padding:0 20px;}

  /* HERO */
  .hero{
    position:relative;overflow:hidden;
    background:
      radial-gradient(ellipse 700px 420px at 82% -10%, #f3c9d8 0%, rgba(243,201,216,0) 60%),
      radial-gradient(ellipse 600px 500px at -10% 100%, var(--pink-pale) 0%, rgba(251,238,243,0) 55%),
      var(--paper);
    padding:64px 20px 56px;
    text-align:center;
    border-bottom:1px solid var(--pink-line);
  }
  .hero img.logo-mark{height:96px;margin:0 auto 22px;}
  .hero h1{
    font-weight:400;
    font-size:clamp(28px,5.4vw,46px);
    line-height:1.18;
    margin:0 0 14px;
    color:var(--maroon-deep);
  }
  .hero p.lede{
    font-size:18px;line-height:1.6;color:#4a2e39;
    max-width:560px;margin:0 auto 30px;
  }
  .hero .cta{display:flex;gap:14px;justify-content:center;flex-wrap:wrap;}
  .btn{
    display:inline-block;padding:12px 26px;
    border:1px solid var(--maroon);
    font-family:inherit;font-size:16px;
    text-decoration:none;cursor:pointer;background:none;
    color:var(--maroon-deep);
    transition:background .18s,color .18s;
  }
  .btn.solid{background:var(--maroon);color:#fff;border-color:var(--maroon);}
  .btn.solid:hover{background:var(--maroon-deep);}
  .btn:not(.solid):hover{background:var(--pink-pale);}

  .rule{border:none;border-top:1px solid var(--pink-line);margin:0;}

  section{padding:56px 20px;}
  h2.section-title{
    font-weight:400;font-size:clamp(24px,3.6vw,32px);
    color:var(--maroon-deep);margin:0 0 8px;text-align:center;
  }
  p.section-sub{text-align:center;color:#6b4a56;font-size:16px;margin:0 0 40px;}

  /* ABOUT */
  .about-grid{display:grid;grid-template-columns:1fr;gap:34px;align-items:start;}
  @media(min-width:760px){.about-grid{grid-template-columns:1.1fr .9fr;}}
  .about-grid p{font-size:17px;line-height:1.75;color:#3a232c;margin:0 0 16px;}
  .pillars{list-style:none;margin:0;padding:0;border-top:1px solid var(--pink-line);}
  .pillars li{
    padding:16px 0;border-bottom:1px solid var(--pink-line);
    display:flex;gap:16px;align-items:baseline;
  }
  .pillars li b{color:var(--maroon);min-width:132px;font-weight:600;font-size:16px;}
  .pillars li span{font-size:15.5px;color:#4a2e39;}

  /* BOARD */
  .lead-officers{
    display:flex;gap:40px;justify-content:center;flex-wrap:wrap;margin-bottom:48px;
  }
  .officer-card{text-align:center;max-width:220px;}
  .officer-card .photo-wrap{
    width:140px;height:140px;border-radius:50%;overflow:hidden;margin:0 auto 14px;
    border:3px solid var(--rose);
  }
  .officer-card .photo-wrap img{width:100%;height:100%;object-fit:cover;}
  .officer-card h3{margin:0 0 2px;font-size:19px;font-weight:600;color:var(--maroon-deep);}
  .officer-card p{margin:0;color:#6b4a56;font-size:14.5px;}

  table.panel{width:100%;border-collapse:collapse;font-size:15.5px;}
  table.panel th{
    text-align:left;color:var(--maroon-deep);border-bottom:1px solid var(--maroon);
    padding:10px 12px;font-weight:600;
  }
  table.panel td{padding:10px 12px;border-bottom:1px solid var(--pink-line);color:#3a232c;}
  table.panel tr:hover td{background:var(--pink-pale);}

  /* EVENTS */
  .event{
    display:grid;grid-template-columns:1fr;gap:22px;margin-bottom:46px;
  }
  @media(min-width:700px){.event{grid-template-columns:1fr 1.15fr;align-items:center;}
    .event.reverse{grid-template-columns:1.15fr 1fr;}
    .event.reverse .event-photo{order:2;}
  }
  .event-photo img{width:100%;border:1px solid var(--pink-line);}
  .event-text .tag{
    font-size:13.5px;color:var(--rose);margin:0 0 6px;letter-spacing:.02em;
  }
  .event-text h3{margin:0 0 10px;font-size:22px;font-weight:600;color:var(--maroon-deep);}
  .event-text p{margin:0;font-size:16px;line-height:1.7;color:#3a232c;}

  /* JOIN / CONTACT */
  .contact-grid{display:grid;grid-template-columns:1fr;gap:36px;}
  @media(min-width:700px){.contact-grid{grid-template-columns:1fr 1fr;}}
  .contact-box h3{margin:0 0 14px;font-size:21px;font-weight:600;color:var(--maroon-deep);}
  .contact-box p{font-size:16px;line-height:1.7;color:#3a232c;margin:0 0 18px;}
  .contact-list{list-style:none;margin:0;padding:0;}
  .contact-list li{padding:12px 0;border-bottom:1px solid var(--pink-line);font-size:16px;}
  .contact-list a{text-decoration:none;color:var(--maroon);}
  .contact-list a:hover{text-decoration:underline;}
  .contact-list .label{color:#6b4a56;display:inline-block;min-width:96px;}

  footer{
    text-align:center;padding:30px 20px 40px;color:#8a6672;font-size:13.5px;
    border-top:1px solid var(--pink-line);
  }
  footer img{height:26px;margin-bottom:10px;opacity:.85;}
</style>
</head>
<body>

<header class="nav">
  <div class="nav-inner">
    <div class="brand" data-nav="home">
      <img src="data:image/png;base64,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 
