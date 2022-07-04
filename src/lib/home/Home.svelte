<script>
  import { navigate } from "svelte-navigator";

  import Navigaion from "../Navigaion.svelte";

  const navigateToBlog = () => {
    navigate("/blog");
  };
  const navigateToWrite = () => {
    navigate("/blog/write");
  };
</script>

<Navigaion />
<div style="position: relative;">
  <div class="imagebox">
    <img src="/background.jpg" alt="Someone Studying" />
  </div>
  <div class="showcase">
    <h1>Stay Touched with <span style="color: #1c8554; background: #eee; padding: .25rem 1rem;">BlogHut</span></h1>
    <div class="hr" />
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Nobis, ipsam.
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Nobis, ipsam
    </p>
    <button class="btn_rio green_btn" on:click={navigateToBlog}>
      Read Blog
    </button>
    <button class="btn_rio white_btn" on:click={navigateToWrite}
      >Write Blog</button
    >
  </div>
</div>

<style>
  .imagebox {
    width: 100%;
    height: 100vh;
    overflow: hidden;
  }
  .imagebox::before {
    position: absolute;
    content: "";
    width: 100%;
    height: 100vh;
    background-color: black;
    opacity: 0.6;
  }
  .imagebox img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .showcase {
    position: absolute;
    top: 30%;
    left: 20%;
    width: 600px;
  }
  .showcase h1 {
    color: white;
  }
  .showcase .hr {
    width: 600px;
    height: 3px;
    background-color: white;
  }
  .showcase p {
    color: white;
    font-size: 18px;
    margin-top: 0.25rem;
    line-height: 28px;
  }
  .btn_rio {
    padding: 0.5rem 1.2rem;
    outline: none;
    border: none;
    text-transform: uppercase;
    font-size: 0.95rem;
    border-radius: 0.25rem;
    margin-top: 0.5rem;
  }
  .green_btn {
    background-color: #1c8554;
    color: white;
  }
  .green_btn:hover {
    background-color: rgb(12, 88, 53);
    box-shadow: 0 4px 2px -2px #4e4e4e;
  }
</style>
