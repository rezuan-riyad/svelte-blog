<script>
  import { Link, navigate } from "svelte-navigator";
  let email, password;

  const handleSubmit = () => {
    console.log(email, password);
    navigate("/", { replace: true });
  };
</script>

<div class="container form-container">
  <h5 class="header">Welcome To BlogHut</h5>
  <form on:submit|preventDefault={handleSubmit}>
    <div class="form-group mb-2">
      <label for="email">Email</label>
      <input class="form-control" type="email" bind:value={email} />
    </div>
    <div class="form-group mb-2">
      <label for="email">Password</label>
      <input class="form-control" type="password" bind:value={password} />
    </div>
    <button class="btn login-btn btn-primary">Login</button>
  </form>
  <div class="d-flex justify-content-between mt-2">
    <Link to="/">Forgot password?</Link>
    <Link to="/signup">Create Account</Link>
  </div>
</div>

<style>
  .header {
    margin-bottom: 1rem;
    text-align: center;
    outline: none;
    font-size: 22px;
  }
  .form-container {
    width: 350px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .login-btn {
    width: 100%;
  }

  button:hover {
    box-shadow: 0px 4px 2px -2px lightgray;
  }
</style>
