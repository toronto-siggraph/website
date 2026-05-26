---
layout: default
title: About Toronto SIGGRAPH
---

<nav style="text-align: right; margin-bottom: 16px; line-height: 1.8;">
  <a href="/">Home</a> &nbsp;|&nbsp;
  <a href="/meetups/">Meetups</a> &nbsp;|&nbsp;
  <strong>About</strong>
</nav>

<img src="/images/logo.png" alt="Toronto ACM SIGGRAPH logo"
     style="max-width: 520px; width: 100%; height: auto; display: block; margin: 1px 0;">

<style>
  .logo-marquee {
    overflow-x: auto;
    overflow-y: hidden;
    width: 100%;
    margin: 20px 0 28px 0;
    padding: 10px 0;
    border-top: 1px solid #ddd;
    border-bottom: 1px solid #ddd;
    cursor: grab;
    -webkit-overflow-scrolling: touch;
    scrollbar-width: none;
  }

  .logo-marquee::-webkit-scrollbar {
    display: none;
  }

  .logo-marquee-track {
    display: flex;
    align-items: center;
    gap: 42px;
    width: max-content;
    padding-right: 42px;
  }

  .logo-marquee img {
    height: 38px;
    width: auto;
    opacity: 0.9;
    flex-shrink: 0;
    pointer-events: none;
    user-select: none;
  }

  .exec-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 20px;
    margin-top: 16px;
    align-items: stretch;
  }

  @media (max-width: 700px) {
    .exec-grid {
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 640px) {
    .logo-marquee {
      margin: 16px 0 24px 0;
      padding: 8px 0;
    }

    .logo-marquee-track {
      gap: 28px;
      padding-right: 28px;
    }

    .logo-marquee img {
      height: 28px;
    }
  }
</style>

<div class="logo-marquee">
  <div class="logo-marquee-track">

    <img src="/images/logo-event-supporters.png" alt="Event supporters">
    <img src="/images/logo-event-supporters-maya.png" alt="Autodesk Maya logo">
    <img src="/images/logo-event-supporters-sideeffects.png" alt="SideFX logo">
    <img src="/images/logo-event-supporters-nvidia.png" alt="NVIDIA logo">
    <img src="/images/logo-event-supporters-sony-pictures.png" alt="Sony Pictures logo">
    <img src="/images/logo-event-supporters.png" alt="Event supporters">
    <img src="/images/logo-event-supporters-imax.png" alt="IMAX logo">
    <img src="/images/logo-event-supporters-ibm.png" alt="IBM logo">
    <img src="/images/logo-event-supporters-dell.png" alt="Dell Technologies logo">
    <img src="/images/logo-event-supporters-paramount-startrek-pixomondo.png" alt="Paramount and Star Trek logos">
    <img src="/images/logo-event-supporters-netflix.png" alt="Netflix logo">

    <img src="/images/logo-event-supporters.png" alt="Event supporters">
    <img src="/images/logo-event-supporters-maya.png" alt="Autodesk Maya logo">
    <img src="/images/logo-event-supporters-sideeffects.png" alt="SideFX logo">
    <img src="/images/logo-event-supporters-nvidia.png" alt="NVIDIA logo">
    <img src="/images/logo-event-supporters-sony-pictures.png" alt="Sony Pictures logo">
    <img src="/images/logo-event-supporters.png" alt="Event supporters">
    <img src="/images/logo-event-supporters-imax.png" alt="IMAX logo">
    <img src="/images/logo-event-supporters-ibm.png" alt="IBM logo">
    <img src="/images/logo-event-supporters-dell.png" alt="Dell Technologies logo">
    <img src="/images/logo-event-supporters-paramount-startrek-pixomondo.png" alt="Paramount and Star Trek logos">
    <img src="/images/logo-event-supporters-netflix.png" alt="Netflix logo">

    <img src="/images/logo-event-supporters.png" alt="Event supporters">
    <img src="/images/logo-event-supporters-maya.png" alt="Autodesk Maya logo">
    <img src="/images/logo-event-supporters-sideeffects.png" alt="SideFX logo">
    <img src="/images/logo-event-supporters-nvidia.png" alt="NVIDIA logo">
    <img src="/images/logo-event-supporters-sony-pictures.png" alt="Sony Pictures logo">
    <img src="/images/logo-event-supporters.png" alt="Event supporters">
    <img src="/images/logo-event-supporters-imax.png" alt="IMAX logo">
    <img src="/images/logo-event-supporters-ibm.png" alt="IBM logo">
    <img src="/images/logo-event-supporters-dell.png" alt="Dell Technologies logo">
    <img src="/images/logo-event-supporters-paramount-startrek-pixomondo.png" alt="Paramount and Star Trek logos">
    <img src="/images/logo-event-supporters-netflix.png" alt="Netflix logo">

  </div>
</div>

<script>
  const marquee = document.querySelector('.logo-marquee');

  let isDown = false;
  let startX = 0;
  let scrollLeft = 0;
  let resumeTimer;

  function autoScrollMarquee() {
    if (!isDown) {
      marquee.scrollLeft += 0.5;

      if (marquee.scrollLeft >= marquee.scrollWidth - marquee.clientWidth - 1) {
        marquee.scrollLeft = 0;
      }
    }

    requestAnimationFrame(autoScrollMarquee);
  }

  marquee.addEventListener('mousedown', (e) => {
    isDown = true;
    marquee.style.cursor = 'grabbing';
    startX = e.pageX - marquee.offsetLeft;
    scrollLeft = marquee.scrollLeft;
    clearTimeout(resumeTimer);
  });

  marquee.addEventListener('mouseleave', () => {
    isDown = false;
    marquee.style.cursor = 'grab';
  });

  marquee.addEventListener('mouseup', () => {
    marquee.style.cursor = 'grab';
    resumeTimer = setTimeout(() => {
      isDown = false;
    }, 600);
  });

  marquee.addEventListener('mousemove', (e) => {
    if (!isDown) return;
    e.preventDefault();
    const x = e.pageX - marquee.offsetLeft;
    const walk = (x - startX) * 1.5;
    marquee.scrollLeft = scrollLeft - walk;
  });

  marquee.addEventListener('touchstart', () => {
    isDown = true;
    clearTimeout(resumeTimer);
  });

  marquee.addEventListener('touchend', () => {
    resumeTimer = setTimeout(() => {
      isDown = false;
    }, 900);
  });

  autoScrollMarquee();
</script>

<h1 style="font-size: 28px; line-height: 1.2; margin-top: 0;">
  <strong>About</strong>
</h1>

<p>
Toronto ACM SIGGRAPH connects professionals, researchers, students, artists, and creators working across computer graphics, interactive media, visualization, AI, VFX, games, animation, and emerging technology.
</p>

<p>
The Toronto chapter is part of ACM SIGGRAPH, the international organization for computer graphics and interactive techniques.
</p>

<h2>Executive Team</h2>

<div class="exec-grid">

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 24px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/bio-hans-avatar-square.png" alt="Hans Bathija" style="width: 140px; height: 140px; object-fit: cover; border-radius: 50%; border: 3px solid #fff; box-shadow: 0 3px 14px rgba(0,0,0,0.16); display: block; margin-bottom: 18px;">

    <h3>Hans Bathija</h3>
    <p><em>Chair</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Computer graphics and emerging technology leadership</strong></li>
      <li><strong>Toronto creative technology community building</strong></li>
    </ul>

    <p>Hans Bathija is Chair of Toronto ACM SIGGRAPH and a long-time Toronto technology and community leader with more than 20 years of international experience across government, enterprise, digital media, and emerging technology initiatives.</p>
    <p>He has founded innovative graphics companies, and has advised governments, Fortune 500 organizations, startups, and not-for-profit institutions across sectors including financial services, healthcare, education, and technology.</p>
    <p>Originally from London, England and now based in Toronto, Hans has served in leadership roles across numerous civic, cultural, and professional organizations, helping build connections between technology, creativity, public service, and community engagement.</p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 24px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/bio-rock-avatar-square.png" alt="Rock Jethwa" style="width: 140px; height: 140px; object-fit: cover; border-radius: 50%; border: 3px solid #fff; box-shadow: 0 3px 14px rgba(0,0,0,0.16); display: block; margin-bottom: 18px;">

    <h3>Rock Jethwa</h3>
    <p><em>Vice Chair</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Enterprise AI transformation, CX, UX, and interactive media systems</strong></li>
      <li><strong>Workflow architecture, service blueprinting, and digital experience strategy</strong></li>
    </ul>

    <p>Rock Jethwa is Vice Chair of Toronto ACM SIGGRAPH and a Toronto-based CX, UX, and Service Design professional with experience spanning enterprise digital transformation projects for Fortune 500 companies and government.</p>
    <p>His early work included contributions to Apple’s internet and browser initiatives during the early growth of the web, along with pioneering 3D graphics and digital heritage projects involving artifact scanning for the Vatican and one of the first digital 3D recreations of the Roman Colosseum.</p>
    <p>Rock remains passionate about building creative technology communities in Toronto and beyond.</p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 24px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/bio-jose-avatar-square.png" alt="Jose Carlos Bringas" style="width: 140px; height: 140px; object-fit: cover; border-radius: 50%; border: 3px solid #fff; box-shadow: 0 3px 14px rgba(0,0,0,0.16); display: block; margin-bottom: 18px;">

    <h3>Jose Carlos Bringas</h3>
    <p><em>Secretary</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Creative technology and organizational coordination</strong></li>
      <li><strong>Community engagement and chapter operations</strong></li>
    </ul>

    <p>Jose Carlos is Secretary of Toronto ACM SIGGRAPH and a Toronto-based creative technologist and technical artist specializing in realtime systems, immersive media, AI-assisted workflows, and interactive experiences.</p>
    <p>His work spans VR, VFX, Unreal Engine, computer vision, motion design, and creative tool development, with a focus on connecting technology, storytelling, and user experience across digital media platforms.</p>
    <p>Jose Carlos is passionate about emerging creative technologies, realtime graphics, and building collaborative communities around computer graphics, interactive media, and innovation.</p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 24px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/bio-alain-avatar-square.png" alt="Alain Chesnais" style="width: 140px; height: 140px; object-fit: cover; border-radius: 50%; border: 3px solid #fff; box-shadow: 0 3px 14px rgba(0,0,0,0.16); display: block; margin-bottom: 18px;">

    <h3>Alain Chesnais</h3>
    <p><em>Treasurer, Chair Emeritus</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>International SIGGRAPH leadership and community building</strong></li>
      <li><strong>Computer graphics industry advocacy and mentorship</strong></li>
    </ul>

    <p>Alain Chesnais is Treasurer and Chair Emeritus of Toronto ACM SIGGRAPH and an internationally recognized leader in computer graphics, interactive media, and creative technology communities.</p>
    <p>He is a past President of ACM SIGGRAPH and has spent decades supporting innovation across digital media, visualization, animation, games, and emerging technology industries around the world.</p>
    <p>Based in Toronto, Alain continues to support the growth of creative technology communities through mentorship, leadership, and international collaboration.</p>
  </div>

</div>

<h2>About the Chapter</h2>

<p>
Toronto ACM SIGGRAPH brings together professionals, students, researchers, artists, developers, and creators working across computer graphics, interactive media, visualization, AI, animation, games, VFX, and emerging technology.
</p>

<p>
The chapter’s mission is to support and grow Toronto’s creative technology community through events, conversations, and collaborations that explore the evolving world of computer graphics and interactive techniques.
</p>

<p>
We aim to expand professional networks, encourage cross-disciplinary exchange, promote public appreciation for computer graphics, and support the broader ACM SIGGRAPH community and conferences around the world.
</p>

<p>
ACM SIGGRAPH is an international organization dedicated to the advancement of computer graphics and interactive techniques through education, research, innovation, and community engagement.
</p>

<footer style="margin-top: 48px; padding-top: 24px; border-top: 1px solid #ddd; font-size: 14px; color: #555; line-height: 1.6;">

  <p>
    <strong>Toronto ACM SIGGRAPH</strong><br>
    Computer graphics. Interactive media. Emerging technology. Community.
  </p>

  <p>
    <a href="/">Home</a> &nbsp;|&nbsp;
    <a href="/meetups/">Meetups</a> &nbsp;|&nbsp;
    <strong>About</strong>
  </p>

  <p>
    Toronto ACM SIGGRAPH is the Toronto professional chapter of ACM SIGGRAPH, connecting creators, researchers, developers, artists, students, and industry professionals across the computer graphics and interactive media community.
  </p>

</footer>
