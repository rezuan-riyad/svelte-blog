<script>
  export let src;
</script>

<div class="userIcon">
  {#if src}
    <img {src} alt="User Icon" class="avatar" />
  {:else}
    <h4 style="text-align: center; margin-top: .25rem;">R</h4>
  {/if}
</div>

<style>
  .userIcon {
    height: 40px;
    width: 40px;
    border-radius: 50%;
    background-color: #e4e4e4;
    overflow: hidden;
    margin: 0 1rem;
  }
  .avatar {
    width: 100%;
    height: 100%;
  }
</style>
