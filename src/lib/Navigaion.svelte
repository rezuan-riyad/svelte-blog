<script>
  let loggedIn = true;
  import { Link } from "svelte-navigator";
  import BurgerIcon from "./styled__components/BurgerIcon.svelte";
  import User from "./styled__components/User.svelte";
  import SeachForm from "./SeachForm.svelte";

  const showLinks = () => {};
</script>

<nav class="navbar fixed-top navbar-expand-md navbar-dark bg-dark">
  <div class="container">
    <a class="navbar-brand" href="#">Navbar</a>
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon" />
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <div class="d-none d-lg-block">
        <SeachForm />
      </div>
      <ul class="navbar-nav ms-auto mb-2 mb-md-0">
        <li class="nav-item">
          <Link class="nav-link active" aria-current="page" to="/">Home</Link>
        </li>
        <li class="nav-item">
          <Link class="nav-link" to="/bloggers">Bloggers</Link>
        </li>
        <li class="nav-item">
          <Link class="nav-link" to="/about">About</Link>
        </li>

        <!-- <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Dropdown
          </a>
          <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><hr class="dropdown-divider"></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </li> -->
      </ul>
      <User src="" />
    </div>
  </div>
</nav>
