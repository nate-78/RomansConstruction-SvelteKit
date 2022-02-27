<script>
  export let link = '';
  export let text = '';
  export let hasWhiteText = false;
  export let className = '';

  import Arrow from './Arrow.svelte';
</script>

<a sveltekit:prefetch 
  href={link} 
  class="{className} {hasWhiteText ? "white-text" : ""}"
>
  <span class="bg"></span>
  <span class="arrow"><Arrow /></span>
  {text}
</a>

<style>
  a {
    position: relative;
    border: 1px solid var(--mustard);
    padding: 8px;
    font-family: var(--font-header);
    text-transform: uppercase;
    font-size: 16px;
    color: var(--deep-blue);
    overflow: hidden;
    margin-top: 1rem;
    margin-bottom: 1rem;
  }
  a.white-text {
    color: white;
  }

  .arrow {
    margin-right: 5px;
  }

  a:hover {
    text-decoration: none;
  }

  a .bg {
    position: absolute;
    display: block;
    top: 0;
    left: 0;
    height: 100%;
    width: 41px;
    border-radius: 0 20px 20px 0;
    background: var(--mustard);
    z-index: -1;
    transition: width .5s;
  }
  a:hover .bg {
    width: 120%;
  }
</style>