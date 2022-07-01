<script>
</script>

<div class="showcase">
  <div class="container-fluid left-section">
    <slot name="left-section" />
  </div>
  <div class="middle-section">
    <slot name="blog-section" />
  </div>
  <div class="container-fluid right-section">
    <slot name="right-section" />
  </div>
</div>

<style>
  .showcase {
    position: relative;
  }
  .left-section {
    position: relative;
  }

  .middle-section {
    width: 600px;
    margin: 0 auto;
  }

  .right-section {
    position: static;
  }
</style>
