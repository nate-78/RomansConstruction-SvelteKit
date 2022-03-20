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
  .top *:not(.pre-heading):not(h2):not(b) {
    font-size: 18px;
  }
  .top slot {
    font-size: 18px;
  }
</style>