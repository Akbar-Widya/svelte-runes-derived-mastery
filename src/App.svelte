<script>
  let count = $state(0);
  let large = $derived(count > 10);
</script>

<!-- click 10 times to change into true -->
<button onclick={() => count++}>
  {large}
</button>