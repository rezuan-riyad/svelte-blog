<script>
  import { createEventDispatcher } from "svelte";
  import Editor from "./Editor.svelte";
  // const dispatch = createEventDispatcher();

  // let title = "";
  let context = "";
  let showModal = false;
  // let errorMessage = "";
  // let charlen = 0;

  const toggleShowModel = (e) => {
    let form = e.target.closest(".form");
    if (form) return;
    showModal = !showModal;
  };

  // const onNewBlogWritten = () => {
  //   if (!title || !context) {
  //     errorMessage = "Title and Context are required.";
  //     return;
  //   } else if (charlen < 150) {
  //     errorMessage =
  //       "Minimum 150 charecters are required to create a blog post.";
  //     return;
  //   }
  //   dispatch("new-blog", {
  //     title: title,
  //     context: context,
  //   });
  // };

  // const calculateCharlen = () => {
  //   charlen = context.replace(/\s/g, "").length;
  // };
</script>

{#if showModal}
  <div class="backdrop" on:click={toggleShowModel}>
    <Editor onCancel={() => (showModal = false)} on:new-blog />
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
