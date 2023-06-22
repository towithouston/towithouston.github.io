<script>
	import EmoticonHappy from 'svelte-material-icons/EmoticonHappy.svelte';
	import Wrench from 'svelte-material-icons/Wrench.svelte';
	import TruckTrailer from 'svelte-material-icons/TruckTrailer.svelte';
	import AccountGroup from 'svelte-material-icons/AccountGroup.svelte';

	import { fly } from 'svelte/transition';
	import { inview } from 'svelte-inview';

	let isInView;

	import Counter from 'svelte-counter';

	const items = [
		{
			count: { count: 584 },
			icon: EmoticonHappy,
			text: 'Clientes Satisfechos'
		},
		{
			count: { count: 1608 },
			icon: Wrench,
			text: 'Órdenes de servicio'
		},
		{
			count: { count: 34 },
			icon: TruckTrailer,
			text: 'Remolques en renta'
		},
		{
			count: { count: 6 },
			icon: AccountGroup,
			text: 'Trabajadores'
		}
	];
</script>

<section
	id="counts"
	class="counts"
	use:inview={{ unobserveOnEnter: true, rootMargin: '-20%' }}
	on:change={({ detail }) => {
		isInView = detail.inView;
	}}
>
	{#if isInView}
		<div class="container">
			<div in:fly={{ y: 200, delay: 250, duration: 1000 }} class="row">
				{#each items as item}
					<div class="col-lg-3 col-md-6">
						<div class="count-box">
							<i class="bx">
								<svelte:component this={item.icon} width="1em" height="1em" color="#dbdd4d" />
							</i>
							<Counter
								values={item.count}
								duration="1000"
								random="false"
								minspeed="10"
								let:counterResult
							>
								<span class="purecounter">{counterResult.count}</span>
							</Counter>

							<p>{item.text}</p>
						</div>
					</div>
				{/each}
			</div>
		</div>
	{/if}
</section>
