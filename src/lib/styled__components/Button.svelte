<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let text;
</script>

<button on:click={() => dispatch("btn-click")}>
  {text}
</button>

<style>
  button {
    border: none;
    outline: none;
    padding: 0.25rem 1rem;
    border-radius: 4px;
    background-color: #212529;
    color: white;
    text-transform: uppercase;
    font-size: 14px;
  }
</style>
