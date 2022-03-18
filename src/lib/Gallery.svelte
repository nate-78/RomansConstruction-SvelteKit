<script>
  import Button from '$lib/controls/Button.svelte';
</script>

<section class="gallery-wrap">
  <div class="container">
    <div class="top">
      <p class="pre-heading">
        Our Gallery
      </p>
      <h2 class="mt-1">
        View Our <b>Past Work</b>
      </h2>
    </div>
  </div>

  <div class="slides">
    <div>
      <img src="images/gallery/img-1.webp" alt="metal roof" />
    </div>
    <div>
      <img src="images/gallery/img-2.webp" alt="shingle roof" />
    </div>
    <div>
      <img src="images/gallery/img-3.webp" alt="shingle roof" />
    </div>
    <div>
      <img src="images/gallery/img-4.webp" alt="exterior repair" />
    </div>
    <div>
      <img src="images/gallery/img-5.webp" alt="metal roof" />
    </div>
  </div>

  <div class="container">
    <div class="btn-wrap">
      <Button link="/gallery" text="View More" />
    </div>
  </div>
</section>

<style>
  .gallery-wrap {
    background-image: url(/images/GreyTriangles.png);
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
  }

  .top {
    text-align: center;
  }

  .slides {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-gap: 10px;
    max-width: 2500px;
    margin: auto;
    margin-bottom: 2rem;
  }

  .btn-wrap {
    display: flex;
    justify-content: center;
  }
</style>