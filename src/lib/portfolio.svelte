<script>
	import ImageLoader from './Image/ImageLoader.svelte';

	import Plus from 'svelte-material-icons/Plus.svelte';
	import Link from 'svelte-material-icons/Link.svelte';
	import { base } from '$app/paths';

	const items = [
		{
			image: 'assets/img/portfolio/double-deck-5-car-hauler-trailer.webp',
			title: 'Mini 5',
			category: 'Car Hauler'
		},
		{
			image: 'assets/img/portfolio/download.webp',
			title: 'Flatbed 1',
			category: 'Flatbed'
		},
		{
			image: 'assets/img/portfolio/images.jpeg',
			title: 'Flatbed 2',
			category: 'Flatbed'
		}
	];
</script>

<section id="portfolio" class="portfolio">
	<div class="container" data-aos="fade-up">
		<div class="section-title">
			<h2>Catálogo de renta</h2>
			<p>
				He aquí una breve descripción de los remolques que tenemos disponibles actualmente:
			</p>
			<p>
			<b>Remolques cuello de ganso (Gooseneck)</b> ideales para transportar maquinaria pesada, 
			vehículos utilitarios y equipos. Cuentan con una pegaña para engancharse directamente al 
			eje trasero del vehículo tractor, lo cual ofrece una mayor maniobrabilidad y estabilidad. 
			Disponibles en diversos tamaños y capacidades.<br/>

			<b>Remolques de plataforma</b>
			Capaces de transportar cargas industriales y comerciales. Cuentan con una plataforma plana 
			sin laterales fijos, perfecta para cargar todo tipo de maquinaria, materiales y equipos. 
			Podemos ofrecer alturas variables y mayor capacidad de carga.<br/>

			<b>Mini remolque para 5 autos</b>
			Pequeño remolque que permite trasladar hasta 5 vehículos compactos o medianos. Cuenta con 
			5 cubiertas independientes que se pliegan hacia arriba, facilitando la carga y descarga de 
			los automóviles. Perfecto para concesionarios, talleres y empresas de transporte.<br/>

			Esos son los principales tipos de remolques que ofrecemos actualmente. Sin embargo, estamos 
			abiertos a atender necesidades especiales y personalizar nuestra oferta según las 
			especificaciones requeridas.
			</p>
		</div>

		<div class="row" data-aos="fade-up" data-aos-delay="100">
			<div class="col-lg-12 d-flex justify-content-center">
				<ul id="portfolio-flters">
					<li data-filter="*" class="filter-active">All</li>
					<li data-filter=".filter-app">Car Hauler</li>
					<li data-filter=".filter-card">Flatbed</li>
				</ul>
			</div>
		</div>

		<div
			class="row portfolio-container"
			data-aos="fade-up"
			data-aos-delay="200"
			style="height: 230px;"
		>
			{#each items as item}
				<div class="col-lg-4 col-md-6 portfolio-item filter-{item.category.toLowerCase()}">
					<div class="portfolio-wrap">
						<ImageLoader
							on:load={onload}
							src={`${base}/` + item.image}
							alt=""
							css_class={'img-fluid'}
						/>
						<div class="portfolio-info">
							<h4>{item.title}</h4>
							<p>{item.category}</p>
							<div class="portfolio-links">
								<a
									href="assets/img/portfolio/portfolio-1.jpg"
									data-gallery="portfolioGallery"
									class="portfolio-lightbox"
									title="App 1"
									><i class="bx">
										<Plus width="1em" height="1em" />
									</i></a
								>
								<a href="/#" title="More Details"
									><i class="bx">
										<Link width="1em" height="1em" />
									</i></a
								>
							</div>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
<!-- End Portfolio Section -->
