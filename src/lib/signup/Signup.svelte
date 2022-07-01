<script>
  import { Link } from "svelte-navigator";
  let email, password, username;

  const handleSubmit = () => {
    console.log(email, password);
  };
</script>

<div class="container form-container">
  <h5 style="text-align:center;" class="mb-4">Signup</h5>
  <form on:submit|preventDefault={handleSubmit}>
    <div class="form-group mb-2">
      <label for="username">Your Name</label>
      <input class="form-control" type="text" bind:value={username} />
    </div>
    <div class="form-group mb-2">
      <label for="email">Email</label>
      <input class="form-control" type="email" bind:value={email} />
    </div>
    <div class="form-group mb-2">
      <label for="password">Password</label>
      <input class="form-control" type="password" bind:value={password} />
    </div>
    <button class="btn login-btn btn-primary">Signup</button>
  </form>
  <div class="mt-2">
    <Link to="/login">Already have an account? Login</Link>
  </div>
</div>

<style>
  .form-container {
    width: 350px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -100%);
  }

  .login-btn {
    width: 100%;
  }

  button:hover {
    box-shadow: 0px 4px 2px -2px lightgray;
  }
</style>
