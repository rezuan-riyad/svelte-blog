<script>
  import MediaCard from "../styled__components/MediaCard.svelte";
  import ShowcaseLayout from "./ShowcaseLayout.svelte";
  import Layout from "../mailLayout/Layout.svelte";
  import WriteBlog from "./WriteBlog.svelte";
  import Navigaion from "../Navigaion.svelte";
  import { onDestroy, onMount } from "svelte";
  import Button from "../styled__components/Button.svelte";

  let totalblogs = [];
  let displayedblogs = [];
  let page = 0;
  let displayBottomLoader = false;

  const fetchMoreBlogs = () => {
    if(page == 10) return;
    page++;
    displayBottomLoader = true;

    setTimeout(() => {
      let temp = totalblogs.slice(displayedblogs.length + 1, page * 10);
      displayedblogs = [...displayedblogs, ...temp];
      displayBottomLoader = false;
    }, 2000);
  };

  const scrollHandler = () => {
    const { scrollTop, scrollHeight, clientHeight } = document.documentElement;
    if (scrollTop + clientHeight >= scrollHeight) {
      fetchMoreBlogs();
    }
  };

  onMount(async (page) => {
    let response = await fetch(`https://jsonplaceholder.typicode.com/posts/`);
    totalblogs = await response.json();
    displayedblogs = totalblogs.slice(0, 10);
    document.addEventListener("scroll", scrollHandler);
  });

  onDestroy(() => {
    document.removeEventListener("scroll", scrollHandler);
  });
</script>

<Layout>
  <div slot="children">
    <ShowcaseLayout>
      <div slot="blog-section">
        <WriteBlog />
        {#each displayedblogs as blog}
          <MediaCard {blog} />
        {/each}
        <div class="text-center mt-3 mb-3">
          {#if displayBottomLoader}
            Loading ...
          {/if}
          <!-- <Button text="Explore More" /> -->
        </div>
      </div>
    </ShowcaseLayout>
  </div>
</Layout>
