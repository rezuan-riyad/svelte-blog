<script>
  import Editor from "../blogs/Editor.svelte";
  import Navigaion from "../Navigaion.svelte";
  import { navigate } from "svelte-navigator";

  const navigateToBlog = () => {
    navigate("/blog");
  };

  const handleNewBlogWriting = () => {
    // TODO: update store
    console.log("TODO: Update Store")
  }
</script>

<Navigaion />
<div class="editor-container">
  <Editor onCancel={navigateToBlog} on:new-blog={handleNewBlogWriting} />
</div>

<style>
  .editor-container {
    position: relative;
    height: 100vh;
  }
</style>
