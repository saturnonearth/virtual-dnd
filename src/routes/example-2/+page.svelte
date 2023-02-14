<script>
	/*
	 * This example shows the result with VirtualList, imported, and un-modified
	 */
	import VirtualList from '$lib/modified-virtual/VirtualList.svelte';

// continue list till 20
	let items = [
		{ id: 1, name: 'item1' },
		{ id: 2, name: 'item2' },
		{ id: 3, name: 'item3' },
		{ id: 4, name: 'item4' },
		{ id: 5, name: 'item5' },
		{ id: 6, name: 'item6' },
	];
</script>

<section>
	<VirtualList listItems={items} width="100%" height={600} itemCount={items.length} itemSize={50}>
		<div slot="item" let:index let:style {style}>
			{items[index].name}
		</div>
	</VirtualList>
</section>

<style>

	div {
		width: 50%;
		padding: 0.2em;
		border: 1px solid blue;
		margin: 0.15em 0;
	}
</style>
