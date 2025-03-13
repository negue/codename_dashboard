<script lang="ts">
  import { onMount } from 'svelte';

  let time: string;

  const updateTime = () => {
    const now = new Date();
    time = now.toLocaleTimeString();
  };

  onMount(() => {
    updateTime();
    const interval = setInterval(updateTime, 1000);
    return () => clearInterval(interval);
  });
</script>

<style>
  .clock {
    font-size: 2em;
    text-align: center;
    padding: 1em;
    border: 1px solid #ccc;
    border-radius: 8px;
    background-color: #f9f9f9;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
</style>

<div class="clock">
  {time}
</div>
