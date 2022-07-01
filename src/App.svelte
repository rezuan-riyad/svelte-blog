<script>
  import { Router, Route, Link } from "svelte-navigator";
  import Home from "./lib/home/Home.svelte";
  import About from "./lib/about/About.svelte";
  import Bloggers from "./lib/bloggers/Bloggers.svelte";
  import Login from "./lib/login/Login.svelte";
  import './lib/styles/main.css'
import Signup from "./lib/signup/Signup.svelte";
  let pathname;
  $: pathname = window.location.pathname;
</script>

<Router>
  <Route path="/login">
    <Login />
  </Route>
  <Route path="/signup">
    <Signup />
  </Route>
  <Route path="/">
    <Home />
  </Route>
  <Route path="/about">
    <About />
  </Route>
  <Route path="/bloggers">
    <Bloggers />
  </Route>
</Router>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
  
</style>
