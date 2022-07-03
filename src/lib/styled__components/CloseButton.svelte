<button class="hide-button">
  <div class="stick_one" />
  <div class="stick_two" />
</button>

<style>
  .hide-button {
    position: absolute;
    height: 24px;
    width: 24px;
    padding-left: 0.25rem;
    border-radius: 50%;
    background: transparent;
    outline: none;
    border: none;
    top: 0;
    right: 0;
  }
  .stick_two,
  .stick_one {
    width: 1px;
    height: 18px;
    background-color: black;
  }
  .stick_one {
    transform: translateX(6px) rotate(45deg);
  }
  .stick_two {
    transform: translateX(6px) translateY(-100%) rotate(-45deg);
  }
</style>
