<script>
  // necessary for triggering parent events
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  const handleAdd = e => dispatch("handleAdd", { e });
  const handleSub = e => dispatch("handleSub", { e });
</script>

<style>
  div {
    display: flex;
    flex-direction: row;
    width: 50%;
    height: 10%;
    align-items: center;
    align-content: center;
    justify-items: center;
    justify-content: space-between;
  }
  button {
    border-color: purple;
    background: plum;
    color: purple;
    border-radius: 5px;
    width: 45%;
    height: 100%;
    cursor: pointer;
  }
  @media screen and (max-width: 600px) {
    div {
      width: 80%;
    }
    button {
      border-radius: 20px;
    }
  }
</style>

<div>
  <button on:click={handleAdd}>ADD</button>
  <button on:click={handleSub}>SUB</button>
</div>
