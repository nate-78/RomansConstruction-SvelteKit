<script>
  export let bannerImg;
  export let titleTopLine;
  export let titleBtmLine;
  export let btnLink;
  export let btnText;
</script>

<div class="banner">
  <image class="banner-img" src="{bannerImg}" alt="{titleTopLine} {titleBtmLine}" />
  <div class="banner-content">
    <h1>
      <span class="top">{titleTopLine}</span>
      <strong>{titleBtmLine}</strong>
    </h1>
    <slot>
      <!-- child content will go here -->
    </slot>
    <a sveltekit:prefetch href="{btnLink}">{btnText}</a>
  </div>
</div>