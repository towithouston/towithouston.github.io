<script>
	import Header from '../lib/header.svelte';
	import Phone from 'svelte-material-icons/Phone.svelte';
	import '../css/bootstrap.css';

	// import `${base}/assets/css/style.css';
</script>

<Header />
<main>
	<slot />
</main>

<a href="tel:+1(305) 833-6104" class="back-to-top d-flex align-items-center justify-content-center active"
	><i class="bi bi-arrow-up-short"><Phone /></i></a
>
