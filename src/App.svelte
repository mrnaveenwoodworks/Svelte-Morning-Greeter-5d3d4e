<script>
  import Greeting from "./components/Greeting.svelte";
  
  let userName = "";
  let showGreeting = false;
  
  function handleSubmit() {
    if (userName.trim()) {
      showGreeting = true;
    }
  }
  
  function resetGreeting() {
    userName = "";
    showGreeting = false;
  }
</script>

<main>
  <div class="container mx-auto px-4 py-8 max-w-md">
    <h1 class="text-2xl font-bold mb-6 text-center">Svelte Morning Greeter</h1>
    
    {#if !showGreeting}
      <div class="bg-white p-6 rounded shadow-md">
        <form on:submit|preventDefault={handleSubmit}>
          <div class="mb-4">
            <label for="userName" class="block mb-2">Enter your name:</label>
            <input 
              type="text" 
              id="userName" 
              bind:value={userName} 
              class="w-full p-2 border border-gray-300 rounded" 
              placeholder="Your Name"
            />
          </div>
          <button 
            type="submit" 
            class="w-full bg-blue-500 text-white py-2 px-4 rounded hover:bg-blue-600"
          >
            Show Greeting
          </button>
        </form>
      </div>
    {:else}
      <div class="bg-white p-6 rounded shadow-md text-center">
        <Greeting name={userName} />
        <button 
          on:click={resetGreeting}
          class="mt-4 bg-gray-200 py-2 px-4 rounded hover:bg-gray-300"
        >
          Reset
        </button>
      </div>
    {/if}
  </div>
</main>

<style>
  :global(body) {
    background-color: #f9f9f9;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  }
</style>