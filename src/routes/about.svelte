<svelte:head>
	<title>About | Franco Valdes | Full Stack Developer | Charlotte NC</title>
	<meta property="og:title" content="About | Franco Valdes | Full Stack Developer | Charlotte NC" />
	<meta property="og:description" content="I am a full stack developer (for hire), husband and dog dad living in Charlotte, NC." />
	<meta property="og:type" content="website" />
	<meta property="og:url" content="http://francovaldes.dev/about" />
	<meta property="og:image" content="favicon/icon.png" />
</svelte:head>
<script>
	import { onMount } from 'svelte';
	import { fly } from 'svelte/transition';
	export let slideNodeList = null;
	export let activeSlide = 0;

	export let slides = [
		{
			mod: null,
			title: 'Today',
			content: 'Today as a Tech Lead and Full Stack Developer, I manage and mentor three frontend and three backend developers. I have helped build many Craft CMS and Craft Commerce sites as well as contributed to numerous open source projects. Every day I try to push boundaries, learning new things and find ways to build things faster and more effeciently.',
			dom: null,
			inView: false,
		},
		{
			mod: 'slide__dark',
			title: 'Appvents & Gym Journal',
			content: 'While at Union, I started to learn about front end technologies and the power they held on the web - and on mobile. I added CSS and JS to my interest and quickly started learning about frameworks like React and Angular to build powerful web and mobile apps. I launched two small apps between 2016 and 2017, Appvents and Gym Journal, both still maintained today.',
			dom: null,
			inView: false,
		},
		{
			mod: 'slide__darker',
			title: 'Union',
			content: 'Wordpress was ok and learning was fun, but I wanted to expand. From Wordpress to Laravel, Laravel to Craft CMS and a whole lot in between, I was finally in a role that would help me grow and develop my skills. Union provided me with everything that I needed; great leadership, mentorship and a great culture.',
			dom: null,
			inView: false,
		},
		{
			mod: 'slide__dark',
			title: 'Xpient',
			content: 'After a small hiatus, I decided to finally persue development as a career. Xpient was my first "real" development job. My roles spanned many disciplines including managing and updating wordpress sites. This was my first dip into the web and it was definetly on the deep end.',
			dom: null,
			inView: false,
		},
		{
			mod: null,
			title: 'Rockslide',
			content: 'From a silly bet to a new career, in 2011 I was challenged by my best friend to build an iPhone game. Never backing down from a challenge, I accepted and started what is now a new found passion and career in development. Few months, an online course, and hundreds of tutorials, I launched my first project, Rockslide.',
			dom: null,
			inView: false,
		},
	];

	const slideTo = (slide, index) => {
		activeSlide = index;
		slide.dom.scrollIntoView({
			behavior: 'smooth'
		});
	}

	const domIndex = (dom) => {
		return slideNodeList.indexOf(dom);
	}

	onMount(() => {
		// kick off observers
		slideNodeList = Array.from(document.querySelectorAll('.slide'));

		let observer = new IntersectionObserver((entries, observer) => {
			entries.forEach((entry) => {
				let index = domIndex(entry.target);

				if (entry.isIntersecting) {
					activeSlide = index;
					slides[index].inView = true;
				}
			});
		}, { threshold: 1 });

		slides.forEach(slide => { observer.observe(slide.dom) });
	})
</script>
<style>
	.about {
		height: 100%;
		width: 100%;
		overflow: auto;
		overflow-x: hidden;
		position: relative;
		scroll-snap-type: mandatory;
		scroll-snap-points-y: repeat(100vh);
		scroll-snap-type: y mandatory;
	}
	.about__back {
		position: fixed;
		top: 16px;
		left: 16px;
		z-index: 999;
	}
	.about__back svg {
    	fill: currentColor;
	}
	.about_controls {
		position: fixed;
		top: 50%;
		left: 32px;
		transform: translate3d(0, -50%, 0);
	}
	.about_controls div {
		border-radius: 50%;
		cursor: pointer;
		height: 12px;
		width: 12px;
		border: 1px solid rgb(10, 168, 44);
		margin-bottom: 8px;
	}
	.about_controls div.active {
		background: rgb(10, 168, 44);
	}
	.slide {
		align-items: center;
		display: flex;
		flex-direction: column;
		height: 100vh;
		justify-content: center;
		width: 100%;
		scroll-snap-align: start;
	}
	.slide_content {
		max-width: 1024px;
		opacity: 0;
		transform: translate3d(0, 25px, 0);
		transition: all 0.3s ease-in-out;
	}
	.slide_content h2 {
		font-size: 10vw;
		line-height: 1;
		margin-bottom: 50px;
	}
	.slide_content p {
		font-size: 2vw;
		padding: 0 75px;
	}
	.slide_content.inView {
		opacity: 1;
		transform: translate3d(0, 0, 0);
	}
	.slide__dark {
		background: #262626;
	}
	.slide__dark * {
		color: #f5f5f5;
	}
	.slide__darker {
		background: #000;
	}
	.slide__darker * {
		color: #f5f5f5;
	}
	@media screen and (min-width: 1440px) {
		.slide_content h2 {
			font-size: 150px;
		}
	}
	@media screen and (max-width: 1024px) {
		.slide_content {
			padding: 0 75px;
		}
		.slide_content p {
			font-size: 2vw;
			line-height: 1.5;
		}
	}
	@media screen and (max-width: 768px) {
		.about__back {
			top: 16px;
			left: 16px;
		}
		.slide_content {
			padding: 0 50px;
		}
		.slide_content h2 {
			font-size: 15vw;
		}
		.slide_content p {
			font-size: 4vw;
			padding: 0 32px;
		}
	}
	@media screen and (max-width: 414px) {
		.slide_content {
			padding: 0 32px;
		}
		.slide_content h2 {
			font-size: 20vw;
		}
		.slide_content p {
			font-size: 5vw;
			padding: 0 32px;
		}
	}
</style>

<div class="about">
	<a href="/" class="about__back">
		<svg width="60px" height="60px" version="1.1" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
			<g>
				<path d="m31.262 53c-1.6562-1.6562-1.6562-4.3438 0-6l27-27v15l-13.5 13.5c-0.82812 0.82812-0.82812 2.1719 0 3l13.5 13.5v15z" />
				<path d="m69.98 42.5v15h-12.148l-6.793-6.793c-0.39062-0.39062-0.39062-1.0234 0-1.4141l6.793-6.793z" />
			</g>
		</svg>
	</a>
	<div class="about_controls">
		{#each slides as slide, i}
			<div class:active={activeSlide === i} on:click={() => slideTo(slide, i)}></div>
		{/each}
	</div>

	{#each slides as slide}
		<div class={slide.mod ? 'slide ' + slide.mod : 'slide' } bind:this={slide.dom}>
			<div class="slide_content" class:inView={slide.inView}>
				<h2>{slide.title}</h2>
				<p>{slide.content}</p>
			</div>
		</div>
	{/each}
</div>
