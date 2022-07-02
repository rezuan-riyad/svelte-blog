<script>
  import Layout from "../mailLayout/Layout.svelte";
</script>

<Layout>
  <div slot="children">
    <div class="content">
      <h4 class="header">Who the hell are we?</h4>
      <div class="image-container">
        <img src="/public/group.jpg" alt="a group" />
      </div>
      <div class="text-container">
        <br />
        <strong>The standard Lorem Ipsum passage, used since the 1500s </strong>
        <p>
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
          minim veniam, quis nostrud exercitation ullamco laboris nisi ut
          aliquip ex ea commodo consequat. Duis aute irure dolor in
          reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
          pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
          culpa qui officia deserunt mollit anim id est laborum." Section
          1.10.32 of "de Finibus Bonorum et Malorum", written by Cicero in 45 BC
          "Sed ut perspiciatis unde omnis iste natus error sit voluptatem
          accusantium doloremque laudantium, totam rem aperiam,
        </p>
        <br />
        <strong>The standard Lorem Ipsum passage, used since the 1500s </strong>
        <p>
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
          minim veniam, quis nostrud exercitation ullamco laboris nisi ut
          aliquip ex ea commodo consequat. Duis aute irure dolor in
          reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
          pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
          culpa qui officia deserunt mollit anim id est laborum." Section
          1.10.32 of "de Finibus Bonorum et Malorum", written by Cicero in 45 BC
          "Sed ut perspiciatis unde omnis iste natus error sit voluptatem
          accusantium doloremque laudantium, totam rem aperiam,
        </p>
      </div>
    </div>
  </div>
</Layout>

<style>
  .content {
    position: absolute;
    top: 0;
    width: 100%;
    height: 300px;
    background-color: #212529;
  }
  .image-container,
  .text-container {
    width: 600px;
    height: auto;
    margin: 0 auto;
  }
  img {
    width: 100%;
    height: 100%;
    margin: 0 auto;
  }
  .header {
    color: white;
    margin-top: 5rem;
    font-size: 28px;
    margin-bottom: 2rem;
  }

  @media only screen and (max-width: 640px) {
    .image-container,
    .text-container {
      width: auto;
      height: auto;
      margin: 0 auto;
      padding: 1rem;
    }
  }
</style>
