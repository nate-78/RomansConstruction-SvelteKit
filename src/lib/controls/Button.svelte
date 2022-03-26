<script>
  export let link = '';
  export let text = '';
  export let hasWhiteText = false;
  export let className = '';
  export let isSubmitBtn = false;

  import Arrow from '../Arrow.svelte';
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  function submit() {
    dispatch('clicked');
  }
</script>

{#if !isSubmitBtn}
  <a sveltekit:prefetch 
    href={link} 
    class="{className} {hasWhiteText ? "white-text" : ""}"
  >
    <span class="bg"></span>
    <span class="arrow"><Arrow /></span>
    <span class="text">{text}</span>
  </a>
{:else}
  <button
    on:click={submit}
    class="{className} {hasWhiteText ? "white-text" : ""}"
    type="submit"
  >
    <span class="bg"></span>
    <span class="arrow"><Arrow /></span>
    <span class="text">{text}</span>
  </button>
{/if}

<style>
  button {
    cursor: pointer;
  }
  
  a, button {
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
    background: none;
    padding-left: 45px;
    justify-content: center;
  }
  a.white-text,
  button.white-text {
    color: white;
  }

  a.no-margin,
  button.no-margin {
    margin: 0;
  }

  .arrow {
    margin-right: 5px;
  }

  a:hover,
  button:hover {
    text-decoration: none;
  }

  a .bg,
  button .bg {
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
  a:hover .bg,
  button:hover .bg {
    width: 120%;
  }
  a .arrow,
  button .arrow {
    position: absolute;
    left: 5px;
    z-index: 1;
  }
  a .text,
  button .text {
    position: relative;
    z-index: 1;
  }

  .tall {
    height: 50px;
  }
</style>