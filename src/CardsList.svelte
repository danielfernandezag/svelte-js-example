<script>
  export let cards;
</script>

<style>
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
  @media screen and (max-width: 600px) {
    #cards-container {
      height: 80%;
      width: 80%;
    }
    .card-item {
      width: 80%;
      border-radius: 20px;
    }
  }
</style>

<div id="cards-container">
  {#each cards as card}
    <div class="card-item">Card: {card.id}</div>
  {/each}
</div>
