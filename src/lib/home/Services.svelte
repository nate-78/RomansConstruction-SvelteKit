<div class="services-wrap" id="services">
  <div class="container">
    <div class="top-section">
      <p class="pre-heading">
        What We Do
      </p>
      <h2 class="mt-1">
        We've got <b>you covered.</b>
      </h2>
      <p class="lg">
        Whether it's your home or business, we make sure our 
        clients have complete satisfaction on every project, 
        every time.
      </p>
    </div>
    <div class="services">
      <div>
        <a href="/commercial" sveltekit:prefetch>
          <img src="images/services/commercial.webp" alt="commercial roofing" />
          <div class="bg-lt"></div>
          <div class="bg-dk"></div>
          <div class="lbl">
            Commercial<br /> Roofing
          </div>
        </a>
      </div>
      <div>
        <a href="/residential" sveltekit:prefetch>
          <img src="images/services/residential.webp" alt="residential roofing" />
          <div class="bg-lt"></div>
          <div class="bg-dk"></div>
          <div class="lbl">
            Residential<br /> Roofing
          </div>
        </a>
      </div>
      <div>
        <a href="/gutters" sveltekit:prefetch>
          <img src="images/services/gutters.webp" alt="gutters" />
          <div class="bg-lt"></div>
          <div class="bg-dk"></div>
          <div class="lbl">
            Gutter Repair <br />
            &amp; Installation
          </div>
        </a>
      </div>
      <div>
        <a href="/exterior-repairs" sveltekit:prefetch>
          <img src="images/services/exterior.webp" alt="exterior repairs" />
          <div class="bg-lt"></div>
          <div class="bg-dk"></div>
          <div class="lbl">
            Exterior<br /> Repairs
          </div>
        </a>
      </div>
    </div>
  </div>
</div>

<style>
  .services-wrap {
    padding-bottom: 50px;
    background-image: linear-gradient(180deg, white, #DBE1E9);
  }
  .top-section {
    text-align: center;
    max-width: 590px;
    margin: auto;
  }
  .services {
    display: grid;
    grid-gap: 1rem;
    grid-template-columns: repeat(4, 1fr);
    margin-top: 2rem;
  }
  .services > div {
    width: 100%;
    height: 350px;
    position: relative;
    border-bottom: 3px solid var(--mustard);
    overflow: hidden;
  }
  .services > div img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
  .services > div .lbl {
    position: absolute;
    bottom: 0;
    text-align: center;
    color: white;
    text-transform: uppercase;
    width: 100%;
    letter-spacing: var(--lspace);
    padding-bottom: .5rem;
  }

  .bg-lt {
    position: absolute;
    background: var(--light-blue);
    width: 120%;
    height: 80px;
    bottom: -15px;
    opacity: .8;
    transform: rotate(-6deg);
    left: -5%;
    transition: .3s;
  }
  .bg-dk {
    position: absolute;
    background: var(--deep-blue);
    width: 120%;
    height: 80px;
    bottom: -15px;
    opacity: .8;
    transform: rotate(6deg);
    left: -5%;
    transition: .3s;
  }

  .services > div:hover .bg-lt,
  .services > div:hover .bg-dk {
    transform: rotate(0);
  }

  @media (max-width: 800px) {
    .services {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  @media (max-width: 400px) {
    .services {
      grid-template-columns: 1fr;
    }
  }
</style>