<script>
	import ImageLoader from './Image/ImageLoader.svelte';

	import TruckTrailer from 'svelte-material-icons/TruckTrailer.svelte';
	import Wrench from 'svelte-material-icons/Wrench.svelte';
	import SwapHorizontal from 'svelte-material-icons/SwapHorizontal.svelte';
	import WrenchClock from 'svelte-material-icons/WrenchClock.svelte';
	import CheckAll from 'svelte-material-icons/CheckAll.svelte';
	import { base } from '$app/paths';

	const tabs = [
		{
			icon: TruckTrailer,
			css_class: ' active show',
			label: 'Servicio de alquiler',
			title: 'Servicio de alquiler de remolques para Hot Shot',
			image: `${base}/assets/img/rent.png`,
			body: 'En Towit Houston usted puede alquilar un remolque para dedicarse al transporte de envío rápido (Hot Shot).',
			bullets: [
				'Alquilar un remolque es menos arriesgado que comprarse uno',
				'Ofrecemos un mantenimiento sin costo en la labor cada 90 días',
				'Remolques totalmentes reparados con gomas nuevas o seminuevas, listos para entrega inmediata'
			]
		},
		{
			icon: Wrench,
			css_class: '',
			label: 'Servicio de reparación',
			title: 'Servicio de reparación de todo tipo de remolques y camionetas',
			image: `${base}/assets/img/repair.jpg`,
			body: 'Towit Houston ejecuta reparaciones completas de remolques y camionetas, lo mismo la parte mecánica que las partes eléctricas. Nuestros servicios más populares son:',
			bullets: [
				'Cambio de frenos eléctricos por hidráulicos',
				'Cancelation EGR',
				'Montaje de goma',
				'Rectificación de tamboras',
				'Alineacion de remolque'
			]
		},
		{
			icon: SwapHorizontal,
			css_class: '',
			label: 'Modificación de remolques',
			title: 'Servicio de modificación de remolques',
			image: `${base}/assets/img/modify.png`,
			body: 'En Towit Houston le hacemos modificaciones a sus remolques para que pueda sacar el máximo de ellos, las modificaciones más comunes son:',
			bullets: [
				'Cambio del tipo Low boy al tipo Flat bed para un áximo aprovechamiento del espacio de carga',
				'Alargamiento de 36 pies a 40 pies para poder acceder a este formato de contenedores',
				'Aumento del número de ejes para soportar cargas más pesadas'
			]
		},
		{
			icon: WrenchClock,
			css_class: '',
			label: 'Servicio de mantenimiento',
			title: 'Servicio de mantenimiento de todo tipo de remolques y camionetas',
			image: `${base}/assets/img/maintenance.jpeg`,
			body: 'En Towit Houston somos especialistas en ejecutar mantenimientos a todos los sistemas de los  remolques y las camionetas. Nuestros mantenimientos más populares son:',
			bullets: [
				'Mantenimiento a ejes',
				'Revision de cableado de luces de remolque',
			]
		}
	];

	function navigate(index) {
		tabs.forEach((tab) => {
			tab.css_class = '';
		});
		tabs[index].css_class = ' active show';
	}
</script>

<section id="tabs" class="tabs">
	<div class="container" data-aos="fade-up">
		<ul class="nav nav-tabs row d-flex">
			{#each tabs as tab, index}
				<li class="nav-item col-3">
					<!-- svelte-ignore a11y-missing-attribute -->
					<button
						on:click={() => navigate(index)}
						class={'nav-link' + tab.css_class}
						data-bs-toggle="tab"
						data-bs-target="#tab-{index + 1}"
					>
						<svelte:component this={tab.icon} width="3em" height="3em" />
						<h4 class="d-none d-lg-block">{tab.label}</h4>
					</button>
				</li>
			{/each}
		</ul>

		<div class="tab-content">
			{#each tabs as tab, index}
				<div class={'tab-pane' + tab.css_class} id="tab-{index + 1}">
					<div class="row">
						<div
							class="col-lg-6 order-2 order-lg-1 mt-3 mt-lg-0"
							data-aos="fade-up"
							data-aos-delay="100"
						>
							<h3>{tab.title}</h3>
							<p class="fst-italic">
								{tab.body}
							</p>
							<ul>
								{#each tab.bullets as bullet}
									<li>
										<CheckAll color="#dbdd4d" />
										{bullet}
									</li>
								{/each}
							</ul>
						</div>
						<div
							class="col-lg-6 order-1 order-lg-2 text-center"
							data-aos="fade-up"
							data-aos-delay="200"
						>
							<ImageLoader src={tab.image} alt="" css_class="my-auto img-fluid" />
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
