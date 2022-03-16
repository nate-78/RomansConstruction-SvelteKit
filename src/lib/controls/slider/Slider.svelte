<script>
  export let numSlides;

  let slideArr = [];
  if (numSlides && numSlides > 0) {
    for (let i = 0; i < numSlides; i++) {
      slideArr.push("");
    }
  }

  const handleClick = (index) => {
    console.log('clicked ' + index);
  };
</script>

<div class="slide-window">
  <div class="slide-track">
    <slot></slot>
  </div>
  {#if numSlides && numSlides > 0}
    <div class="slide-btns">
      {#each slideArr as slide, idx}
        <div on:click={() => handleClick(idx)}></div>
      {/each}
    </div>
  {/if}
</div>

<style>
  .slide-window {
    width: 100%;
    overflow: hidden;
    position: relative;
  }
  .slide-track {
    width: fit-content;
    position: relative;
    left: 0;
    transition: .8s;
  }
  .slide-btns {
    width: 100%;
    position: absolute;
    bottom: 5px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .slide-btns > div {
    width: 10px;
    height: 10px;
    background: var(--med-slate);
    border-radius: 100%;
    margin: .5rem;
    cursor: pointer;
  }
  .slide-btns > div.active {
    background: var(--mustard);
  }
</style>