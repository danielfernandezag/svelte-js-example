<script>
  export let name;
  let counter = 0;
  let cards = [];

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
  #container {
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
  #title {
    color: purple;
    font-size: 2.5rem;
    text-decoration: underline;
  }
  #btn-container {
    display: flex;
    flex-direction: row;
    width: 50%;
    height: 10%;
    align-items: center;
    align-content: center;
    justify-items: center;
    justify-content: space-between;
  }

  #btn-1,
  #btn-2 {
    border-color: purple;
    background: plum;
    color: purple;
    width: 45%;
    height: 100%;
    cursor: pointer;
  }
  #cards-container {
    height: 60%;
    width: 50%;
    max-height: 60%;
    overflow-y: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    align-content: center;
    justify-items: center;
    justify-content: start;
  }
  .card-item {
    text-align: start;
    color: purple;
    border: solid 1px purple;
    background: plum;
    border-radius: 5px;
    padding: 1rem;
    width: 90%;
    margin: 0.5rem 0;
  }
</style>

<div id="container">
  <h1 id="title">{name} {counter}</h1>
  <div id="btn-container">
    <button id="btn-1" on:click={handleAdd}>ADD</button>
    <button id="btn-2" on:click={handleSub}>SUB</button>
  </div>
  <div id="cards-container">
    {#each cards as card}
      <div class="card-item">Card: {card.id}</div>
    {/each}
  </div>
</div>
