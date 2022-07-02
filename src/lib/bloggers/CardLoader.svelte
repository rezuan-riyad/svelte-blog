<div class="row blogger p-sm-3 p-2">
  <div class="col col-12 col-sm-12 col-md-4 image" />
  <div class="col col-12 col-sm-12 col-md-8 position-relative">
    <div class="shine bar1 bar" />
    <div class="shine bar2 bar" />
    <div class="shine bar3 bar" />
    <div class="shine bar4 bar" />
    <div class="shine bar5 bar" />
    <div class="shine bar6 bar" />
  </div>
</div>

<style>
  .blogger {
    background-color: white;
    margin: 1rem;
    border-radius: 8px;
  }
  .image {
    width: 180px;
    height: 150px;
    background-color: gray;
  }

  .bar {

    margin-bottom: 0.75rem;
    width: 50px;
    height: 15px;
    background-color: white;
    background-image: linear-gradient(
      to right,
      #cccccc 0%,
      #d8d8d8 20%,
      #f6f7f8 40%,
      #f6f7f8 100%
    );
    background-repeat: no-repeat;
    background-size: 800px 104px;
    display: inline-block;
    position: relative;
    animation-duration: 1s;
    animation-fill-mode: forwards;
    animation-iteration-count: infinite;
    animation-name: placeholderShimmer;
    animation-timing-function: linear;
  }

  @keyframes placeholderShimmer {
    0% {
      background-position: -150px 0;
    }

    100% {
      background-position: 150px 0;
    }
  }
</style>
