<script>
  export let link = '';
  export let text = '';
  export let hasWhiteText = false;
  export let className = '';

  import Arrow from '../Arrow.svelte';
</script>

<a sveltekit:prefetch 
  href={link} 
  class="{className} {hasWhiteText ? "white-text" : ""}"
>
  <span class="bg"></span>
  <span class="arrow"><Arrow /></span>
  <span class="text">{text}</span>
</a>

<style>
  a {
    position: relative;
    border: 1px solid var(--mustard);
    padding: 8px;
    font-family: var(--font-header);
    text-transform: uppercase;
    font-size: 16px;
    font-weight: 700;
    color: var(--deep-blue);
    overflow: hidden;
    margin-top: 1rem;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
  }
  a.white-text {
    color: white;
  }

  a.no-margin {
    margin: 0;
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
    z-index: 0;
    transition: width .5s;
  }
  a:hover .bg {
    width: 120%;
  }
  a .arrow {
    position: relative;
    z-index: 1;
  }
  a .text {
    position: relative;
    z-index: 1;
  }
</style>