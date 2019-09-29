<script>
  import { createEventDispatcher } from "svelte";
  import {
    ArrowIosBackOutlineIcon,
    ArrowIosForwardOutlineIcon
  } from "svelte-eva-icons";

  export let index;
  export let population;
  export let land;
  export let isNextButtonDisabled;
  export let isPreviousButtonDisabled;

  const dispatch = createEventDispatcher();

  export const handleIncrement = () => dispatch("increment", { index });

  export const handleDecrement = () => dispatch("decrement", { index });
</script>

<style>
  .cta {
    position: absolute;
    display: flex;
    justify-content: space-between;
    align-items: center;
    bottom: 0;
    left: 0;
    width: 41%;
    height: 8rem;
    padding: 2rem 1rem 0rem;
    background: rgb(227, 213, 213, 0.7);
  }

  .cta-info {
    margin: 0;
    padding: 0;
    align-self: flex-start;
    color: #555;
    list-style-type: none;
  }

  .cta-info-item {
    margin-bottom: 1rem;
  }

  .cta-buttons {
    display: flex;
    flex-direction: column;
  }

  .cta-button {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 3rem;
    height: 3rem;
    margin-bottom: 1.5rem;
    border: none;
    outline: none;
    cursor: pointer;
    background: transparent;
    border-radius: 50%;
    transition: background 0.2s ease-in;
  }

  .cta-button:hover:enabled {
    background: rgb(255, 255, 255, 0.9);
  }

  .cta-icon {
    fill: rgb(227, 213, 213);
  }
</style>

<div class="cta">
  <ul class="cta-info">
    <li class="cta-info-item">
      Population: {population}
    </li>
    <li class="cta-info-item">
      Land: {land}
    </li>
  </ul>
  <div class="cta-buttons">
    <button
      class="cta-button"
      on:click={handleIncrement}
      disabled={isNextButtonDisabled}
    >
      <arrow-ios-forward-outline-icon class="cta-icon"/>
    </button>
    <button
      class="cta-button"
      on:click={handleDecrement}
      disabled={isPreviousButtonDisabled}
    >
      <arrow-ios-back-outline-icon class="cta-icon"/>
    </button>
  </div>
</div>

