<script lang="ts" context="module">
	export interface Feature {
		title: string;
		body: string;
	}

	export interface Image {
		src: string;
		alt: string;
		height: number;
		width: number;
	}

	export interface FeatureData {
		image: Image;
		features: Feature[];
	}
</script>

<script lang="ts">
	import { AudioLines } from 'lucide-svelte';
	export let data = {
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

<section id="features" class="py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto max-w-2xl sm:text-center">
			<h2 class="text-base font-semibold leading-7 text-primary">Your Music, Untamed</h2>
			<p class="mt-2 text-3xl font-bold tracking-tight sm:text-4xl">
				Where Inspiration Meets Sound
			</p>
			<p class="mt-6 text-lg leading-8 text-muted-foreground">
				Discover Authentic Recording in the Elkhorn Mountains
			</p>
		</div>
	</div>
	<div class="relative overflow-hidden pt-16">
		<div class="mx-auto max-w-7xl px-6 lg:px-8">
			<img
				src={data.image.src}
				alt={data.image.alt}
				class="mx-auto mb-[-12%] rounded-xl shadow-2xl ring-1 ring-gray-900/10"
				width={data.image.width}
				height={data.image.height}
			/>
			<div class="relative" aria-hidden="true">
				<div class="absolute -inset-x-20 bottom-0 bg-gradient-to-t from-background pt-[7%]"></div>
			</div>
		</div>
	</div>
	<div class="mx-auto mt-16 max-w-7xl px-6 sm:mt-20 md:mt-24 lg:px-8">
		<dl
			class="mx-auto grid max-w-2xl grid-cols-1 gap-x-6 gap-y-10 text-base leading-7 sm:grid-cols-2 lg:mx-0 lg:max-w-none lg:grid-cols-3 lg:gap-x-8 lg:gap-y-16"
		>
			{#each data.features as feature}
				<div class="relative pl-9">
					<dt class="inline font-semibold">
						<AudioLines class="absolute left-1 top-1 h-5 w-5 text-primary" />
						{feature.title}
					</dt>
					<dd class="inline text-muted-foreground">
						{feature.body}
					</dd>
				</div>
			{/each}
		</dl>
	</div>
</section>
