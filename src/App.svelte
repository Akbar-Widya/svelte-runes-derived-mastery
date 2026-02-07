<script>
  let count = $state(0);
  let doubled = $derived(count * 2);
  let numbers = $state([1, 2, 3]);
  let total = $derived.by(() => {
    let total = 0;
    for (const n of numbers) {
      total += n;
    }
    return total;
  })
</script>

<main>
  <button onclick={() => count++}>
    {doubled}
  </button>
  <button onclick={() => numbers.push(numbers.length + 1)}>
    {numbers.join(' + ')} = {total}
  </button>
</main>

<style>
</style>

<!-- In essence, $derived(expression) is equivalent to $derived.by(() => expression) -->

<!-- additionals -->
<!-- To exempt a piece of state from being treated as a dependency, use untrack -->