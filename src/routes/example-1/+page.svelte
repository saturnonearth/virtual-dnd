<script>
	/*
	 * This example shows the result with VirtualList, imported, and un-modified
	 */
	import { dndzone } from 'svelte-dnd-action';
	import VirtualList from 'svelte-tiny-virtual-list';

	let items = [
		{ id: 1, name: 'item1' },
		{ id: 2, name: 'item2' },
		{ id: 3, name: 'item3' },
		{ id: 4, name: 'item4' }
	];
	function handleSort(e) {
		items = e.detail.items;
	}
</script>

<section use:dndzone={{ items }} on:consider={handleSort} on:finalize={handleSort}>
	<VirtualList width="100%" height={600} itemCount={items.length} itemSize={50}>
		<div slot="item" let:index let:style {style}>
			{items[index].name}
		</div>
	</VirtualList>
</section>

<style>
	section {
		width: 50%;
		padding: 0.3em;
		border: 1px solid black;
		/* this will allow the dragged element to scroll the list */
		overflow: scroll;
		height: 200px;
	}
	div {
		width: 50%;
		padding: 0.2em;
		border: 1px solid blue;
		margin: 0.15em 0;
	}
</style>
