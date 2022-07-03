<script>
  import Navigaion from "../Navigaion.svelte";
  import SeachForm from "../SeachForm.svelte";
</script>

<div>
  <Navigaion />

  <div class="children">
    <div class="d-block d-lg-none container">
      <SeachForm />
    </div>
    <slot name="children" />
  </div>
</div>

<style>
  .children {
    margin-top: 4rem;
  }
</style>
