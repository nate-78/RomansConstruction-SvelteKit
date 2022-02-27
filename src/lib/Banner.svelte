<script>
  export let bannerImg;
  export let titleTopLine;
  export let titleBtmLine;
  export let btnLink;
  export let btnText;

  import Button from '$lib/Button.svelte';
</script>

<div class="banner" style="background-image: url({bannerImg})">
  <div class="container">
    <div class="banner-content">
      <h1>
        <span class="top">{titleTopLine}</span>
        <strong>{titleBtmLine}</strong>
      </h1>
      <div class="banner-content-body">
        <slot>
          <!-- child content will go here -->
        </slot>
      </div>
      <Button text={btnText} link={btnLink} hasWhiteText={true} />
    </div>
  </div>
</div>

<style>
  .banner {
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    padding: 100px 0 30px;
    min-height: 60vh;
    color: white;
    display: flex;
    position: relative;
  }
  .banner::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
    background-image: linear-gradient(90deg, rgba(0,0,0,.6), transparent);
  }
  .banner .container {
    display: flex;
  }
  .banner-content {
    height: 100%;
    width: 50%;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    justify-content: center;
    position: relative;
    z-index: 5;
  }
  .banner-content strong {
    color: var(--mustard);
    display: block;
  }
</style>