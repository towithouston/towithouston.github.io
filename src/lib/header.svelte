<script>
	import Menu from 'svelte-material-icons/Menu.svelte';
	import Close from 'svelte-material-icons/Close.svelte';
	import { base } from '$app/paths';

	let icon = Menu;
	let nav_class = '';

	const logo = `${base}/` + 'assets/img/logo.png';

	function toggle() {
		if (icon === Menu) {
			icon = Close;
			nav_class = 'navbar-mobile';
		} else {
			icon = Menu;
			nav_class = '';
		}
	}
	function close() {
			icon = Menu;
			nav_class = '';
	}
</script>

<header id="header" class="fixed-top d-flex align-items-center">
	<div class="container d-flex align-items-center">
		<a href="index.html" class="logo me-2"><img src={logo} alt="" /></a>
		<h1 class="logo me-auto">
			<a href="index.html"><span>Towit Houston</span></a>
		</h1>

		<nav id="navbar" class="navbar {nav_class} order-last order-lg-0">
			<ul>
				<li>
					<a on:click={close} class="nav-link scrollto active" href="#hero">Home</a>
				</li>
				<li>
					<a on:click={close} class="nav-link scrollto" href="#about">Quienes somos</a>
				</li>
				<li>
					<a on:click={close} class="nav-link scrollto" href="#tabs">Servicios</a>
				</li>
				<li>
					<a on:click={close} class="nav-link scrollto" href="#portfolio">Catálogo</a>
				</li>
				<li>
					<a on:click={close} class="nav-link scrollto" href="#team">Equipo</a>
				</li>
				<li>
					<a
						on:click={close}
						href="https://orlandotowit.wordpress.com/"
						target="blank">Blog</a
					>
				</li>
				<li>
					<a on:click={close} class="nav-link scrollto" href="#footer">Contacto</a>
				</li>
			</ul>
			<!-- svelte-ignore a11y-click-events-have-key-events -->
			<i on:click={toggle} class="bi mobile-nav-toggle"
				><svelte:component this={icon} width="1.5em" height="1.5em" color="#dbdd4d" />
			</i>
		</nav>
	</div>
</header>
