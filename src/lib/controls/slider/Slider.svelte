<script>
  export let numSlides;

  let slideArr = [];
  if (numSlides && numSlides > 0) {
    for (let i = 0; i < numSlides; i++) {
      slideArr.push("");
    }
  }

  let cssLeft = 0;
  let activeSlideIdx = 0;

  const handleClick = (index) => {
    console.log('clicked ' + index);
    cssLeft = 100 * index;
    activeSlideIdx = index;
  };
</script>

<div class="slide-window">
  <div class="slide-track" style="left: -{cssLeft}%;">
    <slot></slot>
  </div>
  {#if numSlides && numSlides > 0}
    <div class="slide-btns">
      {#each slideArr as slide, idx}
        <div on:click={() => handleClick(idx)}
          class={idx == activeSlideIdx ? 'active' : ''}  
        ></div>
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
    transition: .8s;
    display: flex;
    flex-wrap: nowrap;
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
    width: 12px;
    height: 12px;
    background: var(--med-slate);
    border-radius: 100%;
    margin: .5rem;
    cursor: pointer;
  }
  .slide-btns > div.active {
    background: var(--mustard);
  }
</style>