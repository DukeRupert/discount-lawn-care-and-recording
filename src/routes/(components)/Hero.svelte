<script lang="ts" context="module">
	export interface HeroData {
		name: string;
		title: string;
		subtext: string;
	}

	let announcement = false;
</script>

<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';

	export let data: HeroData;
</script>

<section id="hero">
	<div class="relative isolate px-6 pt-14 lg:px-8">
		<div
			class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80"
			aria-hidden="true"
		>
			<div
				class="relative left-[calc(50%-11rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-green-500 to-blue-300 opacity-30 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
				style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"
			></div>
		</div>

		<div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-56">
			{#if announcement}
				<div class="hidden sm:mb-8 sm:flex sm:justify-center">
					<div
						class="relative rounded-full px-3 py-1 text-sm leading-6 text-muted-foreground ring-1 ring-gray-900/10 hover:ring-gray-900/20"
					>
						Announcements about new recordings go here. <a
							href="#"
							class="font-semibold text-primary"
							><span class="absolute inset-0" aria-hidden="true"></span>Read more
							<span aria-hidden="true">&rarr;</span></a
						>
					</div>
				</div>
			{/if}
			<div class="text-center">
				<h1
					class="bg-gradient-to-br from-green-500 to-emerald-700 box-decoration-clone bg-clip-text text-4xl font-bold tracking-tight text-transparent sm:text-6xl"
				>
					{data.name}
				</h1>
				<h1 class="text-4xl font-bold tracking-tight sm:text-6xl">
					{data.title}
				</h1>
				<p class="mt-6 text-lg leading-8 text-muted-foreground">
					{data.subtext}
				</p>
				<div class="mt-10 flex items-center justify-center gap-x-6">
					<Button href="#" variant="default">Contact us</Button>
					<Button href="#" variant="outline">Learn more <span aria-hidden="true">→</span></Button>
				</div>
			</div>
		</div>
		<div
			class="absolute inset-x-0 top-[calc(100%-13rem)] -z-10 transform-gpu overflow-hidden blur-3xl sm:top-[calc(100%-30rem)]"
			aria-hidden="true"
		>
			<div
				class="relative left-[calc(50%+3rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 bg-gradient-to-tr from-blue-300 to-green-500 opacity-30 sm:left-[calc(50%+36rem)] sm:w-[72.1875rem]"
				style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"
			></div>
		</div>
	</div>
</section>
