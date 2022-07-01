<script>
  import MediaCard from "../styled__components/MediaCard.svelte";
  import ShowcaseLayout from "./ShowcaseLayout.svelte";
  import WriteBlog from "./WriteBlog.svelte";
  import Navigaion from "../Navigaion.svelte";
</script>

<Navigaion />
<ShowcaseLayout>
  <div slot="blog-section">
    <WriteBlog />
    <MediaCard />
  </div>
</ShowcaseLayout>
