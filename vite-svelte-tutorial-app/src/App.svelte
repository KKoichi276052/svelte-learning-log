<script>
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Counter from './lib/Counter.svelte'
  import Nested from './Nested.svelte'

  let name = 'Svelte'
  let src = svelteLogo
  let string = `this string contains some <strong>HTML!!!</strong>`;

  let count = 0
  $: doubled = count * 2


  function increment() {
    count += 1
  }
</script>



<main>
  <div>
    <!-- template literal to use variable -->
    <h1>Hello {name.toUpperCase()}
      <!-- can be used to HTML attribute. if the variable and attributes share the same name, it can be be written in shorthand ad below -->
      <img {src} alt="" srcset="">
    </h1>
    
    <!-- how to import other components  -->
    <Nested />
    <p>This is a paragraph</p>
    <!-- In case you want to include HTML tag in your variable -->
    <p>{@html string}</p>


    <button on:click={increment}>
    Clicked {count} {count === 1 ? 'time' : 'times'}
    </button>

    <p>{count} doubled is {doubled}</p>

    <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
      <img src={viteLogo} class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>

  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Click on the Vite and Svelte logos to learn more
  </p>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }

  p {
    color: goldenrod;
    font-family: 'Comic Sans MS', cursive;
    font-size: 2em;
  }
</style>
