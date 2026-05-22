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
    width: max-content;
    animation: logoMarquee 36s linear infinite;
  }

  .logo-set {
    display: flex;
    align-items: center;
    gap: 36px;
    flex-shrink: 0;
    padding-right: 36px;
  }

  .logo-marquee img {
    height: 38px;
    width: auto;
    opacity: 0.9;
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

    .logo-set {
      gap: 24px;
      padding-right: 24px;
    }

    .logo-marquee-track {
      animation-duration: 28s;
    }

    .logo-marquee img {
      height: 28px;
    }

  }
</style>

<div class="logo-marquee">
  <div class="logo-marquee-track">

    <!-- LOGO SET 1 -->
    <div class="logo-set">

      <img src="/images/logo-event-supporters.png"
           alt="Event supporters">

      <img src="/images/logo-event-supporters-maya.png"
           alt="Autodesk Maya logo">

      <img src="/images/logo-event-supporters-sideeffects.png"
           alt="SideFX logo">

      <img src="/images/logo-event-supporters-nvidia.png"
           alt="NVIDIA logo">

      <img src="/images/logo-event-supporters-ibm.png"
           alt="IBM logo">

      <img src="/images/logo-event-supporters-dell.png"
           alt="Dell Technologies logo">

      <img src="/images/logo-event-supporters-paramount-startrek-pixomondo.png"
           alt="Paramount, Star Trek, and Pixomondo logos">

    </div>

    <!-- LOGO SET 2 -->
    <div class="logo-set" aria-hidden="true">

      <img src="/images/logo-event-supporters.png" alt="">
      <img src="/images/logo-event-supporters-maya.png" alt="">
      <img src="/images/logo-event-supporters-sideeffects.png" alt="">
      <img src="/images/logo-event-supporters-nvidia.png" alt="">
      <img src="/images/logo-event-supporters-ibm.png" alt="">
      <img src="/images/logo-event-supporters-dell.png" alt="">
      <img src="/images/logo-event-supporters-paramount-startrek-pixomondo.png" alt="">

    </div>

  </div>
</div>
