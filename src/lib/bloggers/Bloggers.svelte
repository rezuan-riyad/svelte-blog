<script>
  import Layout from "../mailLayout/Layout.svelte";
  import Button from "../styled__components/Button.svelte";
  import { onMount } from "svelte";
  import { each } from "svelte/internal";
  import InfoCard from "./InfoCard.svelte";
  import Loader from "../styled__components/Loader.svelte";
  import CardLoader from "./CardLoader.svelte";

  let bloggers = [];
  let loading = true;

  onMount(async () => {
    let response = await fetch("https://jsonplaceholder.typicode.com/users/");
    bloggers = await response.json();
    loading = false;
  });

  const handleHideBlogger = (event) => {
    let temp_id = event.detail;
    bloggers = bloggers.filter((blogger) => blogger.id != temp_id);
  };
</script>

<Layout>
  <div slot="children" class="container content">
    <h1 class="header">Hundred of Professionals with us.</h1>
    <div class="bloggers__data">
      <!-- TODO: Add Grid to display bloggers profile -->
      {#if bloggers}
        {#each bloggers as blogger}
          <InfoCard {blogger} on:hide-blogger={handleHideBlogger} />
        {/each}
      {:else if loading}
        <Loader />
        <!-- TODO: Make a shimmer for loading state (CardLoader) -->
      {/if}

      {#if bloggers.length === 0 && !loading}
      <div style="text-align: center;">
        <p>There's no blogger data to display</p>
      </div>
      {/if}
    </div>
  </div>
  <div>
    <a href="#">See More</a>
  </div>
</Layout>

<style>
  .bloggers__data {
    max-width: 600px;
    margin: 0 auto;
  }
</style>
