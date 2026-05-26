---
layout: default
title: Toronto SIGGRAPH Home
---

<nav style="text-align: right; margin-bottom: 16px; line-height: 1.8;">
  <strong>Home</strong> &nbsp;|&nbsp;
  <a href="/meetups/">Meetups</a> &nbsp;|&nbsp;
  <a href="/about/">About</a>
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

  .coming-soon-card {
    box-sizing: border-box;
    overflow: hidden;
  }

  .coming-soon-layout {
    display: flex;
    gap: 28px;
    flex-wrap: wrap;
    align-items: flex-start;
  }

  .coming-soon-image {
    flex: 0 0 420px;
    max-width: 100%;
  }

  .coming-soon-copy {
    flex: 1;
    min-width: 0;
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

    .coming-soon-card {
      padding: 20px !important;
      border-radius: 24px !important;
    }

    .coming-soon-layout {
      display: block;
    }

    .coming-soon-image {
      max-width: 100%;
      margin-bottom: 20px;
    }

    .coming-soon-copy {
      min-width: 0;
      max-width: 100%;
      overflow-wrap: anywhere;
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

<h1 style="font-family: 'Arial Black', Arial, Helvetica, sans-serif; font-size: 28px; line-height: 1.15; margin-top: 0;">
  Computer graphics. Interactive media. Emerging technology.<br>
  <span style="font-weight: 900; text-transform: uppercase;">Community.</span>
</h1>

<p>
Toronto ACM SIGGRAPH events bring together people working in computer graphics, interactive media, animation, visualization, games, VFX, digital art, and emerging technology.
</p>

<h2>Next Meetup</h2>

<!-- COMING SOON CARD -->
<div class="coming-soon-card"
     style="border: 0px solid #ddd; border-radius: 32px; padding: 4px; margin-top: 4px;">

  <h2 style="font-size: 24px; line-height: 1.1; margin: 0 0 20px 0;">
    ... still rendering ...
  </h2>

  <div class="coming-soon-layout">

    <div class="coming-soon-image">
      <img src="/images/toronto-siggraph-coming-soon-venue.png"
           alt="Toronto SIGGRAPH coming soon event"
           style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border: 1px solid #ddd;">
    </div>

    <div class="coming-soon-copy">

      <p style="margin-top: 0;"><em>Community / Partner Event</em></p>

      <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
        <li><strong>New event announcement coming soon</strong></li>
        <li><strong>Computer graphics and emerging technology community</strong></li>
      </ul>

      <p>Toronto ACM SIGGRAPH is preparing the next community meetup and speaker announcement.</p>

      <p>The chapter connects professionals, students, researchers, artists, and technologists across the GTA.</p>

      <p>Updates will be posted here and on the Events page.</p>

    </div>

  </div>
</div>

<h2>Recent Meetups</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 20px; margin-top: 16px; align-items: stretch;">

  <!-- EVENT 1 -->
  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">

    <img src="/images/toronto-siggraph-amelia-acker-archiving-machines-punch-cards-ai.png"
         alt="Community partner event"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>Archiving Machines: From Punch Cards to Platforms, AI</h3>

    <p><em>Community Partner Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Digital archives in the AI era</strong></li>
      <li><strong>Access, platforms, and historical data systems</strong></li>
    </ul>

    <p>Dr. Amelia Acker explores how archives, machines, and platforms shape access to knowledge.</p>

    <p>The talk connects historical data systems to today’s AI-driven information challenges.</p>

    <p>For researchers, designers, technologists, and digital media practitioners.</p>

    <p><em>Hosted by Thomas Fisher Rare Book Library</em></p>

  </div>

  <!-- EVENT 2 -->
  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">

    <img src="/images/toronto-siggraph-paolo-granata-generative-knowledge.png"
         alt="Paolo Granata event"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>Generative Knowledge: Think, Learn and Create with AI</h3>

    <p><em>Community Partner Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Human creativity and AI collaboration</strong></li>
      <li><strong>Rethinking learning, media, and knowledge</strong></li>
    </ul>

    <p>Dr. Paolo Granata examines how AI is changing the way people think, learn, and create.</p>

    <p>The session looks at creativity as a shared process between humans and intelligent tools.</p>

    <p>For educators, creators, designers, and emerging technology professionals.</p>

    <p><em>Hosted by Rotman School of Management</em></p>

  </div>

   <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-matt-panousis-lipdub-lipsynch-video-ai.png" alt="Toronto SIGGRAPH event"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>Toronto's LipDub.ai and SpaceFlux</h3>

    <p><em>Official Toronto SIGGRAPH Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>AI-powered lip sync and video workflows</strong></li>
      <li><strong>Indie game development and creative technology</strong></li>
    </ul>

    <p>LipDub.ai presented audio-driven AI/ML lip sync rendering for video workflows.</p>
    <p>Indie developer Calin Ardelean shared the creative and technical process behind SpaceFlux.</p>
    <p>For computer graphics, AI media, game development, and interactive technology audiences.</p>

    <p><em>Hosted by George Brown College</em></p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-holiday-gathering-2025.png" alt="Toronto SIGGRAPH holiday gathering"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>Toronto SIGGRAPH Community Holiday Gathering 2025</h3>

    <p><em>Official Toronto SIGGRAPH Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Toronto computer graphics community gathering</strong></li>
      <li><strong>VFX, animation, games, and interactive media networking</strong></li>
    </ul>

    <p>A casual gathering for Toronto’s computer graphics, VFX, animation, and interactive media community.</p>
    <p>The event brings members together to reconnect, meet new people, and close out the year.</p>
    <p>For SIGGRAPH members, students, creators, researchers, and local industry professionals.</p>

    <p><em>Hosted by Toronto ACM SIGGRAPH</em></p>
  </div>

</div>

<div style="margin-top: 28px;">
  <a href="/events/"><strong>View all previous events →</strong></a>
</div>

<footer style="margin-top: 48px; padding-top: 24px; border-top: 1px solid #ddd; font-size: 14px; color: #555; line-height: 1.6;">

  <p>
    <strong>Toronto ACM SIGGRAPH</strong><br>
    Computer graphics. Interactive media. Emerging technology. Community.
  </p>

  <p>
    <strong>Home</strong> &nbsp;|&nbsp;
    <a href="/meetups/">Meetups</a> &nbsp;|&nbsp;
    <a href="/about/">About</a>
  </p>

  <p>
    Toronto ACM SIGGRAPH is the Toronto professional chapter of ACM SIGGRAPH, connecting creators, researchers, developers, artists, students, and industry professionals across the computer graphics and interactive media community.
  </p>

</footer>
