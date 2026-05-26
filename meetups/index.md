---
layout: default
title: Meetups Toronto SIGGRAPH
---

<nav style="text-align: right; margin-bottom: 16px; line-height: 1.8;">
  <a href="/">Home</a> &nbsp;|&nbsp;
  <strong>Meetups</strong> &nbsp;|&nbsp;
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

<h1 style="font-size: 28px; line-height: 1.2; margin-top: 0;">
  <strong>Events</strong>
</h1>

<p>
Toronto ACM SIGGRAPH events bring together people working in computer graphics, interactive media, animation, visualization, games, VFX, digital art, and emerging technology.
</p>

<h2>Upcoming Meetup</h2>

<!-- COMING SOON CARD -->
<div class="coming-soon-card"
     style="border: 0px solid #ddd; border-radius: 32px; padding: 28px; margin-top: 24px;">

  <h2 style="font-size: 32px; line-height: 1.1; margin: 0 0 20px 0;">
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

      <p>Updates will be posted here.</p>
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

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-craig-kaplan-aperiodic-monotiles.png"
         alt="Craig Kaplan Aperiodic Monotiles event"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>Aperiodic Monotiles: The Einstein Tile</h3>

    <p><em>Official Toronto SIGGRAPH Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>The “hat” monotile discovery</strong></li>
      <li><strong>Aperiodic geometry and mathematical tiling theory</strong></li>
    </ul>

    <p>Prof. Craig Kaplan from the University of Waterloo explored the discovery of the first known aperiodic monotile — the “hat” tile.</p>
    <p>The talk covered the history of tiling theory, the search for an “einstein” shape, and related forms including the turtle and spectre tiles.</p>
    <p>For mathematics, procedural graphics, generative design, geometry, and computational art audiences.</p>

    <p><em>Hosted by George Brown College</em></p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-sidefx-houdini-20-jeff-wagner.png"
         alt="SideFX Houdini 20 event with Jeff Wagner"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>SideFX Houdini 20: Technical Innovations</h3>

    <p><em>Official Toronto SIGGRAPH Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>New Houdini 20 features and workflows</strong></li>
      <li><strong>Procedural 3D, VFX, simulation, and technical art</strong></li>
    </ul>

    <p>SideFX Senior Technical Consultant Jeff “Old School” Wagner presented a sneak peek into the technical innovations behind Houdini 20.</p>
    <p>The session explored new features, design decisions, and implementation work behind one of SideFX’s feature-packed releases.</p>
    <p>For VFX artists, technical directors, procedural artists, animators, and computer graphics professionals.</p>

    <p><em>Presented by SideFX</em></p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-metavrse-julie-alan-smithson.png"
         alt="MetaVRse event with Julie Smithson and Alan Smithson"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>MetaVRse: Bringing Metaverse Creation to Everyone</h3>

    <p><em>Official Toronto SIGGRAPH Zoom Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Low-code 3D and immersive web experiences</strong></li>
      <li><strong>XR, spatial computing, enterprise learning, and training</strong></li>
    </ul>

    <p>MetaVRse co-founders Julie Smithson and Alan Smithson joined Toronto SIGGRAPH to discuss their Toronto-based platform for creating and sharing interactive 3D experiences on the web.</p>
    <p>The session explored immersive technology, enterprise XR, digital transformation, and how metaverse creation tools can support learning, training, and communication at scale.</p>
    <p>For XR creators, educators, designers, developers, enterprise teams, and spatial computing professionals.</p>

    <p><em>Zoom event</em></p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-student-volunteer-siggraph-2024.png"
         alt="SIGGRAPH 2024 Student Volunteer information session"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>SIGGRAPH 2024 Student Volunteer Program</h3>

    <p><em>Official Toronto SIGGRAPH Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Careers in VFX, animation, gaming, and CG</strong></li>
      <li><strong>Behind-the-scenes access to the SIGGRAPH conference</strong></li>
    </ul>

    <p>Victoria Lofaro, Communications Lead for the SIGGRAPH Student Volunteer Subcommittee (SVSC), joined Toronto SIGGRAPH to discuss how students can get involved with SIGGRAPH 2024 in Denver.</p>
    <p>The session explored the Student Volunteer program, conference experiences, networking opportunities, and pathways into computer graphics, interactive media, and entertainment industries.</p>
    <p>For students, emerging artists, technical directors, developers, researchers, and future computer graphics professionals.</p>

    <p><em>Featuring past SIGGRAPH Student Volunteers</em></p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-autodesk-maya-25-anniversary.png"
         alt="Autodesk Maya 25th Anniversary Toronto SIGGRAPH event"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>Autodesk Maya 25th Anniversary Celebration</h3>

    <p><em>Official Toronto SIGGRAPH Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>25 years of Maya in film, animation, and VFX</strong></li>
      <li><strong>Autodesk Toronto studio visit and community celebration</strong></li>
    </ul>

    <p>Toronto SIGGRAPH joined Autodesk to celebrate the 25th Anniversary of Maya 1.0 with a special community event at Autodesk’s Toronto headquarters.</p>
    <p>The session highlighted the history and evolution of Maya, the Oscar-winning 3D software used in countless films, games, animation projects, and visual effects pipelines around the world.</p>
    <p>For animators, VFX artists, technical directors, game developers, students, and computer graphics professionals.</p>

    <p><em>Hosted by Autodesk Toronto</em></p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-wefx-houdini-cabinet-of-curiosities.png"
         alt="WeFX Studio Houdini effects presentation"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>WeFX Studio: Houdini FX for Cabinet of Curiosities</h3>

    <p><em>Official Toronto SIGGRAPH Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Advanced Houdini FLIP, VDB, RBD, and Vellum workflows</strong></li>
      <li><strong>Netflix VFX production techniques and creature effects</strong></li>
    </ul>

    <p>WeFX Studio shared advanced Houdini techniques used in Netflix’s <em>Guillermo del Toro’s Cabinet of Curiosities</em>, focusing on lotion simulation and disintegration effects for key characters.</p>
    <p>The presentation explored goo simulations using FLIP and VDB workflows, deforming animated character meshes, and destruction pipelines combining Houdini’s RBD and Vellum toolsets.</p>
    <p>For FX artists, technical directors, Houdini users, VFX students, procedural artists, and computer graphics professionals.</p>

    <p><em>Presented by WeFX Studios</em></p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-yulio-vr-ar-cad-workflows.png"
         alt="Yulio Technologies AR VR CAD event"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>Yulio Technologies: CAD to AR/VR Workflows</h3>

    <p><em>Official Toronto SIGGRAPH Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Bringing CAD models into AR and VR experiences</strong></li>
      <li><strong>3D asset pipelines, rendering, and visualization workflows</strong></li>
    </ul>

    <p>Yulio Technologies presented an inside look at the challenges and opportunities involved in transforming CAD and DCC assets into interactive AR and VR experiences.</p>
    <p>Ian Hall, Chief Product Officer, and Lev Faynshteyn, Head of R&amp;D, discussed rendering pipelines, optimization techniques, and enterprise visualization workflows used across architecture, design, and manufacturing industries.</p>
    <p>For technical artists, XR developers, visualization professionals, engineers, designers, and computer graphics students.</p>

    <p><em>Hosted at the Bahen Centre for Information Technology</em></p>
  </div>

  <div style="border: 1px solid #ddd; border-radius: 8px; padding: 16px; display: flex; flex-direction: column; height: 100%;">
    <img src="/images/toronto-siggraph-dell-technologies-tom-burns-cloud-rendering-ai.png"
         alt="Dell Technologies event with Tom Burns"
         style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; border-radius: 4px; margin-bottom: 12px;">

    <h3>Dell Technologies: Cloud, Rendering, AI and Edge</h3>

    <p><em>Official Toronto SIGGRAPH Event</em></p>

    <ul style="margin-top: 0; margin-bottom: 16px; padding-left: 20px;">
      <li><strong>Real-time rendering, virtual production, and cloud infrastructure</strong></li>
      <li><strong>AI sampling models, object stores, and edge networking</strong></li>
    </ul>

    <p>Tom Burns, UDS Field CTO at Dell Technologies, joined Toronto SIGGRAPH for a technical discussion on modern infrastructure for media, rendering, and emerging production workflows.</p>
    <p>The talk explored whether cloud simply means virtualization, along with trends in real-time rendering, virtual production, AI/statistical sampling models, and federated global namespaces.</p>
    <p>For VFX technologists, rendering specialists, technical directors, infrastructure teams, cloud architects, and computer graphics professionals.</p>

    <p><em>Presented by Dell Technologies</em></p>
  </div>

</div>

<footer style="margin-top: 48px; padding-top: 24px; border-top: 1px solid #ddd; font-size: 14px; color: #555; line-height: 1.6;">

  <p>
    <strong>Interested in speaking, hosting, or partnering with Toronto ACM SIGGRAPH?</strong><br>
    We welcome conversations with people working in computer graphics, animation, VFX, games, visualization, interactive media, and emerging technology.
  </p>

  <p>
    <a href="/">Home</a> &nbsp;|&nbsp;
    <strong>Meetups</strong> &nbsp;|&nbsp;
    <a href="/about/">About</a>
  </p>

  <p>
    Toronto ACM SIGGRAPH connects the local computer graphics and interactive media community through talks, meetups, screenings, workshops, and industry events.
  </p>

</footer>
