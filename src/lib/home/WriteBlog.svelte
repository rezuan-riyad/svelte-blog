<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  let title = "";
  let context = "";
  let showModal = false;
  let errorMessage = "";
  let charlen = 0;

  const toggleShowModel = (e) => {
    let form = e.target.closest(".form");
    if (form) return;
    showModal = !showModal;
  };

  const onNewBlogWritten = () => {
    if (!title || !context) {
      errorMessage = "Title and Context are required.";
      return;
    } else if (charlen < 150) {
      errorMessage = "Minimum 150 charecters are required to create a blog post.";
      return;
    }
    dispatch("new-blog", {
      title: title,
      context: context,
    });
  };

  const calculateCharlen = () => {
    charlen = context.replace(/\s/g, '').length;
  };
</script>

{#if showModal}
  <div class="backdrop" on:click={toggleShowModel}>
    <form class="form" on:submit|preventDefault={onNewBlogWritten}>
      {#if errorMessage}
        <p class="error-text text-danger">{errorMessage}</p>
      {/if}
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
          on:keydown={calculateCharlen}
        />
      </div>
      <p style="text-align: right;">{charlen}/150</p>
      <button type="submit" class="btn btn-primary">Submit</button>
      <button class="btn btn-danger" on:click={() => (showModal = false)}>
        Cancel
      </button>
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
    z-index: 10;
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
    z-index: 100;
    margin: 0 auto;
    position: relative;
    background-color: white;
    border-radius: 8px;
  }

  .error-text {

  }

  @media only screen and (max-width: 640px) {
    .form {
      width: auto;
      min-height: 100vh;
      position: relative;
      margin-top: 2rem;
    }
  }
</style>
