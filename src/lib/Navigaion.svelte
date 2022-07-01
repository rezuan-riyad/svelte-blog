<script>
  let loggedIn = true;
  import { Link } from "svelte-navigator";
import BurgerIcon from "./styled__components/BurgerIcon.svelte";
  import User from "./styled__components/User.svelte";

  const showLinks = () => {

  }
</script>

<nav class="navbar navbar-dark navbar-expand-md bg-dark">
  <div class="container">
    <a class="navbar-brand" href="#">BlogHut</a>
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#navbarNavAltMarkup"
      aria-controls="navbarNavAltMarkup"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <BurgerIcon />
    </button>
    <div class="collapse navbar-collapse">
      <div class="navbar-nav">
        <Link class="nav-link active" aria-current="page" to="/">Home</Link>
        <Link class="nav-link" to="/bloggers">Bloggers</Link>
        <Link class="nav-link" to="/about">About</Link>
      </div>
      <User src="" />
    </div>
  </div>
</nav>

<style>
  .navbar-collapse {
    justify-content: flex-end;
  }
</style>
