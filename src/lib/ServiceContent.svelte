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
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .left {
    margin-right: 2rem;
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
    width: 112px;
    height: 112px;
    background: var(--mustard);
  }
  .main-img img {
    width: 610px;
    margin-left: 150px;
    margin-bottom: 65px;
    position: relative;
  }
  .small-img {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 225px;
  }
  .small-img::before {
    content: '';
    width: 112px;
    height: 112px;
    background: var(--light-blue);
    left: -9px;
    bottom: -3px;
    position: absolute;
  }
  .small-img img {
    position: relative;
  }
</style>