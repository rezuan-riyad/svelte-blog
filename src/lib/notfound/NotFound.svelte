<script>
  import { Link } from "svelte-navigator";
</script>

<div class="container">
  <p><b>404</b> | Sorry this page does not exists.</p>
  <Link to="/">Visit home page instead</Link>
</div>

<style>
  .container {
    position: absolute;
    top: 50%;
    text-align: center;
    transform: translateY(-50%);
  }
</style>
