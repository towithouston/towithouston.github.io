<script>
	import ImageLoader from '../Image/ImageLoader.svelte';

	import { Whatsapp } from 'svelte-simples';
	import Phone from 'svelte-material-icons/Phone.svelte';

	import data from './team.json';
	import { base } from '$app/paths';

	const members = data.members;
</script>

<section id="team" class="team section-bg">
	<div class="container" data-aos="fade-up">
		<div class="section-title">
			<h2>El equipo</h2>
			<p>
				Detrás del éxito de Towit Houston hay cuatro jóvenes trabajadores 
				que ponen todo su esfuerzo diario para brindar el mejor servicio. 
				Con su entusiasmo y profesionalismo, son los que hacen posible que 
				Towit Houston brinde un excelente servicio y experiencia a todos 
				sus clientes.
			</p>
		</div>
		<div class="row">
			{#each members as member}
				<div class="col-lg-3 col-md-6 d-flex align-items-stretch">
					<div class="member" data-aos="fade-up" data-aos-delay="100">
						<div class="member-img">
							<ImageLoader src={`${base}/` + member.image} alt="" css_class={'img-fluid'} />
							<div class="social">
								{#if member.phone}
									<a href={member.phone}><Phone size="1em" color="white" /></a>
								{/if}
								{#if member.whatsapp}
									<a href={member.whatsapp}><Whatsapp size="1em" color="white" /></a>
								{/if}
							</div>
						</div>
						<div class="member-info">
							<h4>{member.name}</h4>
							<span>{member.position}</span>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
