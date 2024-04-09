<script lang="ts" context="module">
	export interface Band {
		title: string;
		link: {
			href: string;
		};
		image?: {
			src: string;
			alt: string;
			width: number;
			height: number;
		};
	}
</script>

<script lang="ts">
	export let data: Band[];
</script>

<section id="logo-cloud" class="py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div
			class="-mx-6 grid grid-cols-2 gap-0.5 overflow-hidden sm:mx-0 sm:rounded-2xl md:grid-cols-3"
		>
			{#each data as band}
				{#if band.image}
					<div class="bg-gray-400/5 p-6 sm:p-10">
						<a href={band.link.href}>
							<img
								class="max-h-12 w-full object-contain"
								src={band.image.src}
								alt={band.image.alt}
								width={band.image.width}
								height={band.image.height}
							/></a
						>
					</div>
				{:else}
					<div class="bg-gray-400/5 p-8 sm:p-10">
						<div class="flex h-12 w-full items-center justify-center text-center">
							<h3 class="text-2xl font-bold tracking-tight sm:text-3xl">{band.title}</h3>
						</div>
					</div>
				{/if}
			{/each}
		</div>
	</div>
</section>
