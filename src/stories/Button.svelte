<script>
  import { createEventDispatcher } from 'svelte';

  export let primary = true;
  export let label = 'Button';
  export let color = 'orange';

  let mode = primary ? '' : 'outline';

  const dispatch = createEventDispatcher();

  function handleClick(event) {
    console.log('I do not do anything yet');
    dispatch('click', event);
  }
</script>

<button on:click={handleClick} class={`${color}  ${mode}`}> {label} </button>

<style>
  button {
    font-weight: 800;
    border-radius: 15px;
    height: 40px;
    font-weight: 600;
    color: white;
    border-style: none;
    padding: 10px 30px;
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
    transition: all cubic-bezier(0.165, 0.84, 0.44, 1) 0.65s;
    outline: none;
    cursor: pointer;
  }

  /* COLORS BACKGROUND */

  .orange {
    background: linear-gradient(180deg, #ffbe0b 0%, #ab2626 100%);
  }

  .purple {
    background: linear-gradient(180deg, #ec35f8 0%, #3c26ab 100%);
  }

  .white {
    background: white;
    color: #066d92;
  }

  .blue {
    background: #11a7dd;
    color: white;
  }

  /* OUTLINE BUTTON */

  .outline {
    color: black;
    position: relative;
    border: solid 2px transparent;
    box-shadow: 2px 1000px 1px #fff inset;
    background-origin: border-box;
  }

  .outline.orange {
    color: #ab2626;
  }

  .outline.white {
    border: solid 2px #066d92;
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
    color: #066d92;
  }
</style>
