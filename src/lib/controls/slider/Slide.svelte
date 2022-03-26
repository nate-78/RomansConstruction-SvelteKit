<script>
  export let width;
</script>

<div style="width: {width}px">
  <slot></slot>
</div>

<style>
  div {
    /* width: 660px; */
    height: 100%;
  }
</style>