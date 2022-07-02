<script>
  import MediaCard from "../styled__components/MediaCard.svelte";
  import ShowcaseLayout from "./ShowcaseLayout.svelte";
  import Layout from "../mailLayout/Layout.svelte";
  import WriteBlog from "./WriteBlog.svelte";
  import Navigaion from "../Navigaion.svelte";
</script>

<Layout>
  <div slot="children">
    <ShowcaseLayout>
      <div slot="blog-section">
        <WriteBlog />
        <MediaCard />
        <MediaCard />
        <MediaCard />
        <MediaCard />
      </div>
    </ShowcaseLayout>
  </div>
</Layout>
