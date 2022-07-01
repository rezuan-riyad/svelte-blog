<script>
  let title;
  let context;
  let showModal = true;

  const toggleShowModel = (e) => {
    let form = e.target.closest(".form");
    if (form) return;
    showModal = !showModal;
  };
</script>

{#if showModal}
  <div class="backdrop" on:click={toggleShowModel}>
    <form class="form">
      <div class="form-group mb-2">
        <label for="title" class="mb-1">Blog Tilte</label>
        <input class="form-control" placeholder="Title" bind:value={title} />
      </div>
      <div class="form-group mb-2">
        <label for="title" class="mb-1">Blog Post</label>
        <textarea
          class="form-control"
          rows={10}
          placeholder="Write your post"
          bind:value={context}
        />
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
{:else}
  <button class="btn btn-primary mt-4" on:click={toggleShowModel}>
    Write Blog
  </button>
{/if}

<style global>
  .backdrop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  .backdrop::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: black;
    opacity: 0.5;
  }

  .form {
    width: 600px;
    height: 500px;
    padding: 2rem 3rem;
    top: 50%;
    transform: translateY(-50%);
    z-index: 10000;
    margin: 0 auto;
    position: relative;
    background-color: white;
    border-radius: 8px;
  }
</style>
