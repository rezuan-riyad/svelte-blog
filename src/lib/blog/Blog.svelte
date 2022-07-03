<script>
  import { onMount } from "svelte";
  import { useParams, useNavigate } from "svelte-navigator";
  import Navigaion from "../Navigaion.svelte";
  import OnlineChecker from "../OnlineChecker.svelte";

  const params = useParams();
  const navigate = useNavigate();

  let blogId = $params.id;
  let dataFetching = true;
  let errorMessage = "";
  let blog;
  let blogger = {
    id: null,
    name: "",
    username: "",
  };

  let imgsrc;

  const fetchData = async () => {
    try {
      const blogRes = await fetch(
        `https://jsonplaceholder.typicode.com/posts/${blogId}`
      );
      const blogData = await blogRes.json();
      if (blogData) blog = blogData;

      const userRes = await fetch(
        `https://jsonplaceholder.typicode.com/users/${blog.userId}`
      );
      const bloggerData = await userRes.json();
      if (bloggerData) blogger = bloggerData;

      if (parseInt(blogId) % 2 == 0) {
        imgsrc = `https://randomuser.me/api/portraits/women/${blogger.id}.jpg`;
      } else {
        imgsrc = `https://randomuser.me/api/portraits/men/${blogger.id}.jpg`;
      }

      dataFetching = false;
      errorMessage = "";
    } catch (error) {
      errorMessage = "Something went wrong.";
      console.log(error);
    }
  };

  onMount(async () => {
    fetchData();
  });

  const handleBackOnline = async () => {
    if (!blog || !blogger.id) {
      setTimeout(() => {
        console.log("Data Should Be Fetched");
        fetchData();
      }, 2000);
    }
    return;
  };

  $: console.log(blogger);
</script>

<Navigaion />
<div class="row container">
  <div class="col-md-2 col-lg-3">
    <button class="btn mb-2 back-btn" on:click={() => navigate(-1)}>
      <ion-icon name="arrow-back-outline" />
    </button>
  </div>
  <div class="col col-12 col-md-8 col-lg-6">
    {#if dataFetching && window.navigator.onLine}
      <p>Loading....</p>
    {:else if dataFetching && !window.navigator.onLine}
      <OnlineChecker on:back-online={handleBackOnline} />
    {/if}

    {#if blog}
      <div class="card">
        <h1>{blog.title}</h1>
      </div>
      <div class="card">
        <div>
          <img src={imgsrc} alt={blogger.username} />
        </div>
        <p>{blogger.name}</p>
        <p>{blog.body}</p>
      </div>
    {/if}
  </div>
</div>

<style>
  .container {
    margin: 0 auto;
    margin-top: 5rem;
  }

  .card {
    background-color: white;
    border-radius: 8px;
    padding: 1rem;
    margin: 0 auto;
    margin-bottom: 1rem;
  }
  .back-btn {
    outline: none;
    border: none;
    box-shadow: none;
    float: right;
  }
  .back-btn:hover {
    background-color: rgb(199, 199, 199);
  }
  h1 {
    font-size: 22px;
    line-height: 28px;
  }
  @media only screen and (max-width: 540px) {
    .container {
      padding: 0;
    }
    .col {
      padding: 0;
    }
    .card {
      border-radius: 0;
      border: none;
      margin-bottom: 0.5rem;
    }
    .back-btn {
      display: none;
    }
  }
</style>
