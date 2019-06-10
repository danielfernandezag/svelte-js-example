<script>
  import Buttons from "./Buttons.svelte";
  import CardsList from "./CardsList.svelte";
  // props recieved are declared with export and can have default values if not recieved or undefined from parent
  export let name = "";
  // state variables are declared normally
  let counter = 0;
  let cards = [];
  // methods
  const handleAdd = () => {
    const newCards = cards;
    counter++;
    newCards.push({ id: counter });
    cards = newCards;
  };
  const handleSub = () => {
    if (counter === 0) {
      counter = 0;
    } else {
      const newCards = cards;
      newCards.pop();
      cards = newCards;
      counter--;
    }
  };
</script>

<style>
  div {
    border: solid 1px #adff2f;
    border-radius: 5px;
    width: 100%;
    height: 99%;
    display: flex;
    flex-direction: column;
    align-content: center;
    align-items: center;
    justify-content: center;
    justify-items: center;
    background: #acff2f8f;
  }
  h1 {
    color: purple;
    font-size: 2.5rem;
    text-decoration: underline;
  }
  @media screen and (max-width: 600px) {
    div {
      border-radius: 20px;
      height: 100%;
    }
  }
</style>

<div>
  <h1>{name} {counter}</h1>
  <Buttons on:handleAdd={handleAdd} on:handleSub={handleSub} />
  <CardsList {cards} />
</div>
