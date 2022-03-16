<script>
  export let name;
  export let location;
</script>

<div class="quote-wrap">
  <div class="quote-content">
    <div class="icon">"</div>
    <div class="copy">
      <slot></slot>
      <div class="attribution">
        {name} <br>
        <span>{location}</span>
      </div>
    </div>
  </div>
</div>

<style>
  .quote-wrap {
    width: 100%;
    padding-top: 30px;
  }
  .quote-content {
    padding: 50px 0;
    background: white;
    position: relative;
    width: 90%;
    margin: auto;
  }
  .icon {
    position: absolute;
    width: 60px;
    height: 60px;
    top: -30px;
    border-radius: 100%;
    background: var(--mustard);
    color: white;
    font-size: 36px;
    font-weight: 700;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: serif;
    left: calc(50% - 25px);
    box-shadow: 0 2px 5px rgba(0 0 0 / 30%);
  }

  .copy {
    font-size: 18px;
    color: var(--font-color);
    max-width: 400px;
    margin: auto;
  }
  .attribution {
    text-transform: uppercase;
    font-weight: 700;
    color: var(--med-slate);
    letter-spacing: var(--lspace);
  }
  .attribution span {
    color: var(--light-blue);
    font-size: 14px;
    letter-spacing: .5px;
  }
</style>