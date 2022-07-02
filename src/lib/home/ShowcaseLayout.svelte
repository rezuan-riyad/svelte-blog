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

  @media only screen and (max-width: 640px) {
    .middle-section {
      padding: 0 1rem;
      width: auto;
    }
    .right-section {
      display: none;
    }

    .left-section {
      display: none;
    }
  }
</style>
