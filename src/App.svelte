<script>
/**
 * Derived and reactivity
 * When you bind to or modify a selected object that points to an element within a deeply reactive array, 
 * the changes automatically sync back to the original array.
*/
let items = $state([]);

let index = $state(0);
let selected = $derived(items[index]);

/**
 * Destructuring
 * If you use destructuring with a $derived declaration, 
 * the resulting variables will all be reactive.
*/
let { a, b, c } = $derived(stuff());

// is roughly equivalent to:
let _stuff = $derived(stuff());
let a = $derived(_stuff.a);
let b = $derived(_stuff.b);
let c = $derived(_stuff.c);
</script>