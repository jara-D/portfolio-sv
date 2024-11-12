<script>
	import { page, navigating } from '$app/stores';
	import NavIcon from './nav-Icon.svelte';
</script>

<svelte:head>
	<title>
		{$page.url.pathname === '/' ? 'Home' : $page.url.pathname.split('/').pop()}
	</title>
</svelte:head>

<nav>
	<ul>
		<li class="icon">
			<a href="/">
				<NavIcon />
			</a>
		</li>
		<li class={$page.url.pathname === '/' ? 'active' : ''}>
			<a href="/" aria-current={$page.url.pathname === '/'}>Home</a>
		</li>
		<li class={$page.url.pathname === '/about' ? 'active' : ''}>
			<a href="/about" aria-current={$page.url.pathname === '/about'}>About me</a>
		</li>
		<li class={$page.url.pathname === '/projects' ? 'active' : ''}>
			<a href="/projects" aria-current={$page.url.pathname === '/projects'}>Projecten</a>
		</li>
		<li class={$page.url.pathname === '/contact' ? 'active' : ''}>
			<a href="/contact" aria-current={$page.url.pathname === '/contact'}>Contact</a>
		</li>
		<li>
			{#if $navigating}
				wefwef
			{/if}
		</li>

	</ul>
</nav>

<style>
	nav {
		position: fixed;
		top: 0;
		width: 100%;
		z-index: 10;
		backdrop-filter: blur(20px) saturate(2);
		background-color: rgba(31, 93, 134, 0.7);
	}
	nav:after {
		content: '';
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 97%;
		border-bottom: var(--accent-color) 0.2rem solid;
	}
	nav a {
		text-decoration: none;
		color: var(--text-color);
		font-size: calc(1rem + 0.5vw);
		padding: 0px 10px 0 10px;
	}
	ul {
		position: relative;
		display: flex;
		align-items: center;
		width: 100%;
		height: 3rem;
		z-index: 5;
	}

	ul > li {
		height: 100%;
		display: flex;
		align-items: center;
	}
	ul > li:first-child {
		margin-left: 1rem;
	}
	li.active > a {
		color: var(--main-color);
	}
	li.active {
		background-color: var(--accent-color);
		border-bottom: var(--main-color) 0.2rem solid;
	}
	ul {
		list-style-type: none;
		padding: 0;
		margin: 0;
		display: flex;
	}
	.icon > a {
		display: flex;
		align-items: center;
		justify-content: center;
		height: 80%;
		width: auto;
	}


	@keyframes spin {
		0% {
			transform: rotate(0deg);
		}
		100% {
			transform: rotate(360deg);
		}
	}
</style>
