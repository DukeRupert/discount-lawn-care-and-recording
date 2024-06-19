<script lang="ts">
	import type { HeroData } from './(components)/Hero.svelte';
	import Hero from './(components)/Hero.svelte';
	import type { Band } from './(components)/LogoCloud.svelte';
	import LogoCloud from './(components)/LogoCloud.svelte';
	import type { FeatureData } from './(components)/Features.svelte';
	import Features from './(components)/Features.svelte';
	import Pricing from './(components)/Pricing.svelte';

	const hero_data: HeroData = {
		name: '406 Records',
		title: 'Where Your Music Comes Alive',
		subtext:
			'Coming soon! Immerse your music in the raw beauty of Montana. 406 Records, your high-fidelity studio in the Elkhorn Mountains.'
	};

	const logo_cloud_data: Band[] = [
		{
			title: 'Transistor',
			link: {
				href: '#'
			},
			image: {
				src: 'https://tailwindui.com/img/logos/158x48/transistor-logo-gray-900.svg',
				alt: 'Transistor',
				width: 158,
				height: 48
			}
		},
		{
			title: 'Reform',
			link: {
				href: '#'
			},
			image: {
				src: 'https://tailwindui.com/img/logos/158x48/reform-logo-gray-900.svg',
				alt: 'Reform',
				width: 158,
				height: 48
			}
		},
		{
			title: 'Tuple',
			link: {
				href: '#'
			},
			image: {
				src: 'https://tailwindui.com/img/logos/158x48/tuple-logo-gray-900.svg',
				alt: 'Tuple',
				width: 158,
				height: 48
			}
		},
		{
			title: 'Laravel',
			link: {
				href: '#'
			},
			image: {
				src: 'https://tailwindui.com/img/logos/158x48/laravel-logo-gray-900.svg',
				alt: 'Laravel',
				width: 158,
				height: 48
			}
		},
		{
			title: 'SavvyCal',
			link: {
				href: '#'
			},
			image: {
				src: 'https://tailwindui.com/img/logos/158x48/savvycal-logo-gray-900.svg',
				alt: 'SavvyCal',
				width: 158,
				height: 48
			}
		},
		{
			title: 'Statamic',
			link: {
				href: '#'
			},
			image: {
				src: 'https://tailwindui.com/img/logos/158x48/statamic-logo-gray-900.svg',
				alt: 'Statamic',
				width: 158,
				height: 48
			}
		}
	];

	const feature_data: FeatureData = {
		image: {
			src: 'https://as2.ftcdn.net/v2/jpg/03/50/71/87/1000_F_350718780_JN2Dtmkw7tcOp73YCipPCxHaACycUsbe.jpg',
			alt: 'Elkhorn mountain range',
			height: 665,
			width: 1000
		},
		features: [
			{
				title: 'The Elkhorn Mountain Experience',
				body: 'Record surrounded by the majestic Elkhorn Mountains, where the vast Montana landscape fuels your creativity.'
			},
			{
				title: 'Authenticity Amplified',
				body: 'Capture the organic spirit of your music within a studio designed to reflect the natural beauty of its setting.'
			},
			{
				title: 'Passionate Partners',
				body: 'Collaborate with technicians who care deeply about preserving the true essence of your art.'
			},
			{
				title: 'Find Your Sound, Find Your Story',
				body: 'Uncover the unique narrative within your music, guided by a team dedicated to your artistic vision.'
			},
			{
				title: 'Immersive Retreats',
				body: 'Disconnect from the world and focus solely on your music with multi-day recording packages.'
			},
			{
				title: 'Explore Montana',
				body: 'Tap into the wild spirit of the region during breaks – hike, fish, or simply soak in the breathtaking views.'
			}
		]
	};
</script>

<Hero data={hero_data} />
