<script lang="ts">
	import Header from '../header.svelte';
	import type { Item } from './timeline';
	import TimelineItem from './timeline_item.svelte';

	const createItem = (company: String, position: String, dateStart: String): Item => {
		return { company, position, dateStart };
	};

	let items: Item[] = [
		createItem(
			'Sberbank',
			'DevOps Engineer',
			'Feb 2018'
		),
		createItem('«Газпром нефть»', 'Ведущий специалист', 'Sep 2019 - Nov 2020'),
		createItem(
			'Luxoft',
			"Infra Cloud Support",
			'Nov 2020 - Dec 2021'
		),
		createItem('ЛАНИТ', 'DevOps Engineer', 'Dec 2021 - Jun 2024'),
		createItem('AlfaBank', 'SRE Engineer', 'Jun 2021 - Now')
	];
</script>

<div class="timeline">
	<Header accent="yellow" text="experience" />
	<div class="separator" />
	<ul>
		{#each items as item}
			<li>
				<TimelineItem {item} />
			</li>
		{/each}
	</ul>
</div>

<style lang="scss">
	.timeline {
		width: 100%;
		grid-area: timeline;
	}

	.separator {
		display: block;
		width: 100%;
		border-bottom: 2px dashed var(--black2);
		margin-bottom: -1.2em;
		margin-top: 1em;
	}

	ul {
		display: flex;
		align-content: space-evenly;
		float: left;
		width: 100%;
		list-style: none;
		padding: 0;
	}

	@media only screen and (max-width: 1200px) {
		.separator {
			display: none;
		}

		ul {
			margin-top: -0.5em;
			border-left: 2px dashed var(--black2);
			flex-direction: column;
		}
	}
</style>
