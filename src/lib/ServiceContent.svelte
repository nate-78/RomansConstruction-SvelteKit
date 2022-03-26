<script>
  export let lgImg;
  export let lgImgAlt;
  export let smImg;
  export let smImgAlt;
  export let preHeading;
  export let heading;
  export let svcList = [];
</script>

<section>
  <div class="container">
    <div class="row">
      <div class="left">
        <div class="main-img">
          <img src={lgImg} alt={lgImgAlt} />
        </div>
        <div class="small-img">
          <img src={smImg} alt={smImgAlt} />
        </div>
      </div>
      <div class="right">
        <p class="pre-heading">
          {preHeading}
        </p>
        <h2 class="mt-1">{heading}</h2>
        <slot></slot>
        {#if svcList && svcList.length > 0}
          <ul>
            {#each svcList as svc}
              <li>{svc}</li>
            {/each}
          </ul>
        {/if}
      </div>
    </div>
  </div>
</section>

<style>
  .row {
    align-items: center;
    display: grid;
    grid-template-columns: 8fr 4fr;
    grid-gap: 3rem;
  }
  .left {
    position: relative;
  }
  .right {
    width: 375px;
    min-width: 375px;
    max-width: 375px;
  }

  .main-img {
    position: relative;
  }
  .main-img::before {
    position: absolute;
    right: -9px;
    top: -9px;
    content: '';
    width: 18%;
    height: unset;
    aspect-ratio: 1;
    background: var(--mustard);
  }
  .main-img img {
    width: 75%;
    margin-left: 25%;
    margin-bottom: 11%;
    position: relative;
  }
  .small-img {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 31%;
    aspect-ratio: 1;
  }
  .small-img::before {
    content: '';
    width: 52%;
    aspect-ratio: 1;
    background: var(--light-blue);
    left: -9px;
    bottom: -3px;
    position: absolute;
  }
  .small-img img {
    position: relative;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  @media (max-width: 1000px) {
    section {
      padding-top: 10px;
    }
  }

  @media (min-width: 767px) and (max-width: 900px) {
    .small-img {
      display: none;
    }
    .main-img img {
      margin: 0;
      width: 100%;
    }
  }

  @media (max-width: 767px) {
    .row {
      display: flex;
      flex-direction: column-reverse;
      grid-gap: 1rem;
    }
    .right {
      min-width: 550px;
      max-width: 550px;
    }
  }

  @media (max-width: 630px) {
    .right {
      min-width: 100%;
      max-width: 100%;
    }
  }

  @media (max-width: 400px) {
    .small-img {
      display: none;
    }
    .main-img img {
      margin: 0;
      width: 100%;
    }
  }
</style>