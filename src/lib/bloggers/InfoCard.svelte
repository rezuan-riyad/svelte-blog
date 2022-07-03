<script>
  import Button from "../styled__components/Button.svelte";
  import { createEventDispatcher } from "svelte";
  export let blogger;
  let closeBtn = false;
  let following;
  const dispatch = createEventDispatcher();

  const showCloseBtn = () => {
    closeBtn = true;
  };
  const hideCloseBtn = () => {
    closeBtn = false;
  };

  const hideBlogger = () => {
    dispatch("hide-blogger", blogger.id);
  };

  const handleFollow = () => {
    // TODO: Fetch update 
    following = true;
  };
</script>

<div
  class="row blogger p-sm-3 p-2"
  on:mouseenter={showCloseBtn}
  on:mouseleave={hideCloseBtn}
>
  <div class="col col-12 col-sm-12 col-md-4" />
  <div class="col col-12 col-sm-12 col-md-8 position-relative">
    <p><b>{blogger.name}</b></p>
    <p>Email: {blogger.email}</p>
    <p>Phone: {blogger.phone}</p>
    <p>Work Place: {blogger.company.name}</p>
    <p>Website: {blogger.website}</p>
    <p>
      Address: {blogger.address.city}, {blogger.address.street}, {blogger
        .address.zipcode}
    </p>
    <div class="d-flex">
      <Button
        text={following ? "Following" : "Follow"}
        on:btn-click={handleFollow}
      />
    </div>
    {#if closeBtn}
      <button class="hide-button" on:click={hideBlogger}>
        <div class="stick_one" />
        <div class="stick_two" />
      </button>
    {/if}
  </div>
</div>

<style>
  .blogger {
    background-color: white;
    margin: 1rem;
    border-radius: 8px;
  }
  .blogger:hover {
    box-shadow: 0px 0px 8px lightgray;
  }
  .hide-button {
    position: absolute;
    height: 24px;
    width: 24px;
    padding-left: 0.25rem;
    border-radius: 50%;
    background: transparent;
    outline: none;
    border: none;
    top: 0;
    right: 0;
  }
  .stick_two,
  .stick_one {
    width: 1px;
    height: 18px;
    background-color: black;
  }
  .stick_one {
    transform: translateX(6px) rotate(45deg);
  }
  .stick_two {
    transform: translateX(6px) translateY(-100%) rotate(-45deg);
  }
</style>
