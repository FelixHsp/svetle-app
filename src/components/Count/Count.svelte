<script lang="ts">
	let count: number = 0;
	let numbers: number[] = [1, 2, 3, 4];

	$: doubled = count * 2;

	$: console.log(`the count is ${count}`);

	$: sum = numbers.reduce((pre, cur) => pre + cur, 0);

	const handleClick = () => {
		count += 1;
	};

	const addNumber = () => {
		numbers = [...numbers, numbers.length + 1];
	};
</script>

<button on:click={handleClick}>
	Clicked {count} {count === 1 ? 'time' : 'times'}
</button>
<p>
	{count} doubled is {doubled}
</p>

<p>{numbers.join(' + ')} = {sum}</p>
<button on:click={addNumber}>Add a number</button>