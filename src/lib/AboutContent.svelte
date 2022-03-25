<script>
  export let preheading;
  export let headingLight;
  export let headingBold;
  export let img;
  export let imgAlt;
</script>

<section>
  <div class="container">
    <div class="top">
      <p class="pre-heading">
        {preheading}
      </p>
      <h2 class="mt-1">
        {headingLight}
        <b>{headingBold}</b>
      </h2>
      <slot name="topSlot"></slot>
    </div>
    <div class="btm">
      <div class="left">
        <img src={img} alt={imgAlt} />
      </div>
      <div class="right">
        <slot name="btmSlot"></slot>
      </div>
    </div>
  </div>
</section>

<style>
  section {
    padding-top: 0;
  }
  .top {
    text-align: center;
    max-width: 585px;
    margin: auto;
  }
  .top {
    font-size: 18px;
  }

  .btm {
    display: grid;
    grid-template-columns: 2fr 1fr;
    grid-gap: 2rem;
    align-items: center;
  }

  .btm .left img {
    width: 100%;
  }

  .btm .right {
    font-size: 18px;
    text-align: center;
  }
</style>