<script>
  import { Router, Route, Link } from "svelte-navigator";
  import Home from "./lib/home/Home.svelte";
  import Blogs from "./lib/blogs/Blogs.svelte";
  import About from "./lib/about/About.svelte";
  import Bloggers from "./lib/bloggers/Bloggers.svelte";
  import Login from "./lib/login/Login.svelte";
  import Blog from "./lib/blog/Blog.svelte";
  import "./lib/styles/main.css";
  import Signup from "./lib/signup/Signup.svelte";
  import NotFound from "./lib/notfound/NotFound.svelte";
  import WriteNew from "./lib/writeNewBlog/WriteNew.svelte";
import { component_subscribe } from "svelte/internal";
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

  <Route path="/blog/write" component={WriteNew} />
  <Route path="/blog/*"> 
    <Route path="/" component={Blogs} />
    <Route path=":id" component={Blog} />
  </Route>
  <Route path="/about" component={About} />
  <Route path="/bloggers" component={Bloggers} />
  <Route path="*" component={NotFound} />
</Router>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
</style>
