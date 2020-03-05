<script>
  import Pepp from "./Pepp.svelte";

  let todos = [];

  function addTodo() {
    todos = [...todos, ""];
  }

  function removeTodo(index) {
    todos = todos.filter(todo => todos.indexOf(todo) != index);
  }
</script>

<style>
  button {
    font-family: "Arial";
    font-weight: bold;
    height: 2rem;
    font-size: 1.2rem;
  }

  input {
    background-color: whitesmoke;
    height: 1.8rem;
    font-size: 1.2rem;
  }

  h1 {
    color: black;
    font-size: 5rem;
    font-family: "Shadows Into Light";
    font-weight: bold;
  }

  .add {
    background-color: rgb(15, 177, 15);
    margin-top: 1rem;
  }

  .remove {
    background-color: red;
    margin-left: 0.5rem;
  }

  .maindiv {
    text-align: center;
  }

  .pepp {
    text-align: center;
  }
</style>

<div class="maindiv">
  <h1>Todolist</h1>
  {#each todos as todo, index}
    <input bind:value={todos[index]} />
    <button class="remove" on:click={() => removeTodo(index)}>Delete</button>
    <br />
  {/each}
  <button class="add" on:click={addTodo}>Add</button>
</div>
<div class="pepp">
  <Pepp />
</div>
