<script>
  import { createEventDispatcher, onDestroy, onMount } from "svelte";

  const dispatch = createEventDispatcher();

  let errorMessage = "";
  let success = "";

  const beingOnline = () => {
    errorMessage = "";
    success = "Back online";
    dispatch("back-online");
  };

  onMount(() => {
    if (!window.navigator.onLine) {
      errorMessage = "Make sure you have an active internet connection.";
    }

    window.addEventListener("online", beingOnline);
  });

  onDestroy(() => {
    window.removeEventListener("online", beingOnline);
  });
</script>

<div>
  {#if errorMessage && !success}
    <p class="text-danger">{errorMessage}</p>
  {:else if success}
    <p class="text-success">{success}</p>
  {/if}
</div>
