<script>
  import Navigaion from "../Navigaion.svelte";
</script>

<div>
  <Navigaion />
  <div class="children">
    <slot name="children"></slot>
  </div>
</div>

<style>
  .children {
    margin-top: 4rem;
  }
</style>