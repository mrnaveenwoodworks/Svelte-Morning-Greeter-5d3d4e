<script>
  import { onMount } from "svelte";
  
  export let name = "Friend";
  
  let greeting = "";
  let timeOfDay = "";
  let currentHour = 0;
  
  onMount(() => {
    const now = new Date();
    currentHour = now.getHours();
    
    if (currentHour >= 5 && currentHour < 12) {
      greeting = "Good morning";
      timeOfDay = "morning";
    } else if (currentHour >= 12 && currentHour < 18) {
      greeting = "Good afternoon";
      timeOfDay = "afternoon";
    } else {
      greeting = "Good evening";
      timeOfDay = "evening";
    }
  });
</script>

<div class="greeting-container">
  <h1>{greeting}, {name}!</h1>
  
  {#if timeOfDay === "morning"}
    <p>Have a wonderful start to your day!</p>
    <div class="icon">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 256 256" width="40" height="40"><rect width="256" height="256" fill="none"/><line x1="128" y1="36" x2="128" y2="32" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><circle cx="128" cy="128" r="56" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="60" y1="60" x2="56" y2="56" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="60" y1="196" x2="56" y2="200" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="196" y1="60" x2="200" y2="56" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="196" y1="196" x2="200" y2="200" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="36" y1="128" x2="32" y2="128" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="128" y1="220" x2="128" y2="224" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="220" y1="128" x2="224" y2="128" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/></svg>
    </div>
  {:else if timeOfDay === "afternoon"}
    <p>Hope your day is going well!</p>
    <div class="icon">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 256 256" width="40" height="40"><rect width="256" height="256" fill="none"/><line x1="128" y1="36" x2="128" y2="32" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><circle cx="128" cy="128" r="56" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="60" y1="60" x2="56" y2="56" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="60" y1="196" x2="56" y2="200" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="196" y1="60" x2="200" y2="56" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="196" y1="196" x2="200" y2="200" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="36" y1="128" x2="32" y2="128" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="128" y1="220" x2="128" y2="224" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="220" y1="128" x2="224" y2="128" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/></svg>
    </div>
  {:else}
    <p>Have a peaceful evening!</p>
    <div class="icon">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 256 256" width="40" height="40"><rect width="256" height="256" fill="none"/><line x1="208" y1="120" x2="208" y2="72" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="232" y1="96" x2="184" y2="96" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="160" y1="32" x2="160" y2="64" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><line x1="176" y1="48" x2="144" y2="48" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/><path d="M210.69,158.18A96.78,96.78,0,0,1,192,160,96.08,96.08,0,0,1,97.82,45.31,88,88,0,1,0,210.69,158.18Z" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="24"/></svg>
    </div>
  {/if}
</div>