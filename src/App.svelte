<script>
  let books = ['Learning Svelte', 'The Zen of Cooking Tea'];
  let newBook = '';

  function addBook(event) {
    if (event.key === 'Enter') {
      books = [...books, newBook];
      newBook = '';
    }
  }
</script>

<label>
  <h3>Add Book</h3>
  <input type="text" bind:value={newBook} on:keydown={addBook} />
</label>
<h4>My Books</h4>
<ul>
  {#each books as book}
    <li>{book}</li>
  {/each}
</ul>

<style>
  h3 {
    font-size: 3rem;
    color: darkcyan;
    font-weight: 600;
  }
  h4 {
    font-size: 1.75rem;
    font-weight: 400;
    font-family: 'Courier New', Courier, monospace;
  }
  ul {
    list-style: none;
  }
  ul li {
    color: aqua;
  }
</style>