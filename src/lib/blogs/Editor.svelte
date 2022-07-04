<script>
  import { createEventDispatcher } from "svelte";
  
  export let onCancel;

  const dispatch = createEventDispatcher();
  let title = "";
  let context = "";
  let errorMessage = "";
  let charlen = 0;

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
  <button class="btn btn-danger" on:click={onCancel}>
    Cancel
  </button>
</form>


<style>

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

  @media only screen and (max-width: 640px) {
    .form {
      width: auto;
      min-height: 100vh;
      position: relative;
      margin-top: 2rem;
      padding: 2rem 1rem;
    }
  }
</style>