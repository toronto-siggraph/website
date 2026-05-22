<nav style="text-align: right; margin-bottom: 16px; line-height: 1.8;">
  <a href="/">Home</a> &nbsp;|&nbsp;
  <a href="/events/">Events</a> &nbsp;|&nbsp;
  <a href="/about/">About</a>
</nav>

<img src="/images/logo.png" alt="Toronto ACM SIGGRAPH logo"
     style="max-width: 520px; width: 100%; height: auto; display: block; margin: 1px 0;">

<!-- INDUSTRY LOGO MARQUEE -->
<style>
  .logo-marquee {
    overflow: hidden;
    width: 100%;
    margin: 20px 0 28px 0;
    padding: 10px 0;
    border-top: 1px solid #ddd;
    border-bottom: 1px solid #ddd;
  }

  .logo-marquee-track {
    display: flex;
    align-items: center;
    gap: 36px;
    width: max-content;
    animation: logoMarquee 28s linear infinite;
  }

  .logo-marquee img {
    height: 38px;
    width: auto;
    opacity: 0.6;
    filter: grayscale(100%);
    flex-shrink: 0;
  }

  @keyframes logoMarquee {
    from {
      transform: translateX(0);
    }
    to {
      transform: translateX(-50%);
    }
  }

  /* Mobile responsive adjustments */
  @media (max-width: 640px) {

    .logo-marquee {
      margin: 16px 0 24px 0;
      padding: 8px 0;
    }

    .logo-marquee-track {
      gap: 24px;
      animation-duration: 22s;
    }

    .logo-marquee img {
      height: 28px;
    }

  }
</style>

<div class="logo-marquee">
  <div class="logo-marquee-track">

    <!-- First set -->
    <img src="/images/logo-event-supporters.png" alt="Toronto Supporters">
    <img src="/images/logo-event-supporters-maya.png" alt="Autodesk Maya logo">
    <img src="/images/logo-event-supporters-sideeffects.png" alt="Side Effects logo">
    <img src="/images/logo-event-supporters-nvidia.png" alt="Nvidia logo">
    <img src="/images/logo-event-supporters-ibm.png" alt="IBM logo">
    <img src="/images/logo-event-supporters-paramount-starteck-pixomondo.png" alt="Paramount Star Trek logo">

    <!-- Duplicate set for seamless scrolling -->
    <img src="/images/logo-event-supporters.png" alt="Toronto Supporters">
    <img src="/images/logo-event-supporters-maya.png" alt="Autodesk Maya logo">
    <img src="/images/logo-event-supporters-sideeffects.png" alt="Side Effects logo">
    <img src="/images/logo-event-supporters-nvidia.png" alt="Nvidia logo">
    <img src="/images/logo-event-supporters-ibm.png" alt="IBM logo">
    <img src="/images/logo-event-supporters-paramount-starteck-pixomondo.png" alt="Paramount Star Trek logo">

  </div>
</div>

<p>
Toronto ACM SIGGRAPH events bring together people working in computer graphics, interactive media, animation, visualization, games, VFX, digital art, and emerging technology.
</p>

<h2>Upcoming Meetup</h2>

<!-- COMING SOON CARD -->
<div style="border: 1px solid #ddd; border-radius: 32px; padding: 28px; margin-top: 24px;">

  <h2 style="font-size: 32px; line-height: 1.1; margin: 0 0 20px 0;">
    Still rendering ...
  </h2>

  <div style="display: flex; gap: 28px; flex-wrap: wrap; align-items: flex-start;">

    <div style="flex: 0 0 420px; max-width: 100%;">
      <img src="/images/toronto-siggraph-coming-soon-venue.png"
           alt="Toronto SIGGRAPH coming soon event"
           style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border: 1px solid #ddd;">
    </div>

    <div style="flex: 1; min-width: 280px;">
      <p style="margin-top: 0;"><em>Community / Partner Event</em></p>

      <p><strong>
        Update coming soon for next meetup.
      </strong></p>

    </div>

  </div>
</div>

<h2>Recent Meetups</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 20px; margin-top: 16px; align-items: stretch;">

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-amelia-acker-archiving-machines-punch-cards-ai.png" alt="Community partner event"
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

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-paolo-granata-generative-knowledge.png" alt="Paolo Granata event"
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

</div>
