<script>
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';

	export let visible = false;
	export let status = 'introstart';
	export let flashlight = null;

	const typewriter = (node, { speed = 50 }) => {
		const valid = (
			node.childNodes.length === 1 &&
			node.childNodes[0].nodeType === 3
		);

		if (!valid) return {};

		const text = node.textContent;
		const duration = text.length * speed;

		return {
			duration,
			tick: (t, u) => {
				const i = ~~(text.length * t);
				node.textContent = text.slice(0, i);
			}
		};
	}

	const mousemove = (e) => {
		const { currentTarget } = e;
		currentTarget.style.setProperty('--xy', `${e.x}px ${e.y}px`);
	}

	const touchmove = (e) => {
		const touch = e.touches[0];
		const { target } = touch;

		flashlight.style.setProperty('--xy', `${touch.clientX}px ${touch.clientY}px`);
	}

	const mousedown = (e) => {
		const { currentTarget } = e;
		currentTarget.style.setProperty('--r', '60vh');
	}

	const mouseup = (e) => {
		const { currentTarget } = e;
		currentTarget.style.setProperty('--r', '30vh');
	}

	onMount(() => {
		visible = true;
	});
</script>
<style>
	.home {
		--xy: 50% 50%;
		--r: 30vh;

		align-items: flex-start;
		background: radial-gradient(circle at var(--xy), #0000, #eeef var(--r));
		display: flex;
		height: 100%;
		width: 100%;
		user-select: none;
	}
	.home > div {
		flex: 1;
	}
	.home__heading {
		padding: 15vh 32px;
		max-width: 1024px;
		margin: 0 auto;
	}
	.home__heading h1 {
		font-size: 12vw;
		line-height: 1;
		margin-bottom: 50px;
	}
	.home__heading h2 {
		font-size: 75px;
		line-height: 1;
		margin-bottom: 50px;
	}
	.home img {
		position: absolute;
		right: 0;
		bottom: 0;
		height: 100%;
		object-fit: cover;
		z-index: -1;
		transform: translate3d(50%, 0, 0);
	}
	.home img:last-child {
		left: 0;
		height: unset;
		transform: none;
		width: 100%;
		object-fit: unset;
		z-index: -2;
	}

	@media screen and (min-width: 1440px) {
		.home__heading h1 {
			font-size: 170px;
		}
	}

	@media screen and (max-width: 1024px) {
		.home__heading h2 {
			font-size: 6vw;
			line-height: 1.5;
		}
	}

	@media screen and (max-width: 400px) {
		.home__heading {
			padding: 25vh 32px;
		}

		.home__heading h1 {
			margin-bottom: 25px;
		}

		.home__heading h2 {
			margin-bottom: 25px;
		}
	}
</style>

<svelte:head>
	<title>Franco Valdes | Full Stack Developer | Charlotte NC</title>
	<meta property="og:title" content="Franco Valdes | Full Stack Developer | Charlotte NC" />
	<meta property="og:description" content="I am a full stack developer (for hire), husband and dog dad living in Charlotte, NC." />
	<meta property="og:type" content="website" />
	<meta property="og:url" content="http://francovaldes.dev" />
	<meta property="og:image" content="favicon/icon.png" />
</svelte:head>

<div class="home" bind:this={flashlight} on:touchmove={touchmove} on:mousemove={mousemove} on:mousedown={mousedown} on:mouseup={mouseup}>
	<div class="home__heading">
		{#if visible}
			<h1 in:fade>Franco<br/>Valdes</h1>
			<h2 in:typewriter="{{ speed: 50 }}" on:introend="{() => status = 'complete'}">I am a full stack developer, husband and dog dad living in Charlotte, NC.</h2>
		{/if}
		{#if status === 'complete'}
			<div>
				<a href="/about" title="About Me" class="button" in:fly="{{ y: 25, delay: 150, duration: 500 }}">About</a>
				<a href="/work" title="My Work" class="button" in:fly="{{ y: 25, delay: 300, duration: 500 }}">Work</a>
				<a href="mailto:franco.valdes89@gmail.com?subject=I want to hire you" title="My Work" class="button" in:fly="{{ y: 25, delay: 450, duration: 500 }}">Contact</a>
			</div>
		{/if}
	</div>
	<img src="assets/me.png" alt="me" />
	<img src="assets/charlotte-skyline.png" alt="Charlotte" />
</div>
