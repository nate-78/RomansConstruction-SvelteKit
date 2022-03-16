<script>
	import { fade } from 'svelte/transition';

	let menuOpen = false;

	const handleClick = () => {
		menuOpen = !menuOpen;
	}
</script>

<header>
	<div class="container">
		<div class="logo">
			<a href="/">
				<img src="images/Romans_Logo_White.webp" alt="Roman's Construction" />
			</a>
		</div>

		<nav>
			<div class="menu-btn {menuOpen ? 'open' : ''}" 
				on:click={handleClick} 
			>
				<span></span>
				<span></span>
				<span></span>
			</div>
			{#if menuOpen}
				<ul transition:fade>
					<li>
						<a href="/">Link 1</a>
					</li>
					<li>
						<a href="/">Link 2</a>
					</li>
				</ul>
			{/if}
		</nav>
	</div>
</header>

<style>
	header {
		padding: 30px 0;
		background: transparent;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		z-index: 99;
		color: white;
	}

	.logo a {
		display: inline-block;
		padding: 5px;
		position: relative;
	}
	.logo img {
		width: 250px;
		display: block;
	}
	.logo a::before {
		content: '';
		position: absolute;
		top: 50%;
		left: 50%;
		height: 0;
		width: 0;
		transition: .3s;
		background-color: var(--mustard);
		opacity: .8;
		z-index: -1;
	}
	.logo a:hover::before {
		left: 0;
		top: 0;
		width: 100%;
		height: 100%;
	}

	header .container {
		display: flex;
		width: 100%;
		justify-content: space-between;
		align-items: center;
	}

	.menu-btn {
		width: 33px;
		height: 33px;
		border-radius: 100%;
		background: var(--mustard);
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		cursor: pointer;
		position: relative;
		z-index: 999;
	}

	.menu-btn span {
		background: white;
		display: block;
		margin: 2px;
		width: 18px;
		height: 1.5px;
		transition: .3s;
		position: relative;
		transform: rotate(0);
	}

	.menu-btn.open span:nth-child(2) {
		opacity: 0;
	}
	.menu-btn.open span:first-child {
		transform: rotate(45deg);
		top: 6px;
	}
	.menu-btn.open span:last-child {
		transform: rotate(-45deg);
		bottom: 5px;
	}

	nav ul {
		position: fixed;
		left: 0;
		top: 0;
		background: rgba(255 255 255 / 90%);
		width: 100%;
		height: 100%;
		z-index: 99;
		list-style: none;
		margin: 0;
		padding: 30px;
		text-align: center;
	}
	nav ul li {
		margin: .5rem 0;
	}
	nav ul li a {
		color: var(--deep-blue);
		transition: .3s;
		font-size: 1.5rem;
		font-weight: 700;
	}
	nav ul li a:hover {
		color: var(--med-slate);
		text-decoration: none;
	}
	
</style>
