<script lang="ts">
	import { SITE_DATA } from '$lib/global';
	import { navigating } from '$app/stores';
	import { MenuIcon } from 'lucide-svelte';
	import { Separator } from '$lib/components/ui/separator/index.js';
	import { Button } from '$lib/components/ui/button';
	import * as Sheet from '$lib/components/ui/sheet';
	import Lightswitch from './Lightswitch.svelte';

	let is_mobile_open = false;

	interface Quote {
		quote: string;
		author: string;
	}

	function getRandomQuote(): Quote {
		const randomIndex = Math.floor(Math.random() * quotes.length);
		return quotes[randomIndex];
	}

	const quotes: Quote[] = [
		{
			quote: 'Sometimes you get the bear, and sometimes the bear gets you.',
			author: 'Montana Proverb'
		},
		{
			quote:
				"Montana is a great place to raise a family, and it's also a great place to raise hell.",
			author: 'Ivan Doig'
		},
		{ quote: 'Give me a horse with guts and a bad disposition any day.', author: 'Will Rogers' },
		{
			quote: 'The West is the best place to get lost – the worst place to find yourself.',
			author: 'Anonymous'
		},
		{
			quote:
				'The air was so clear a coyote two miles away could hear your heart beat. Or maybe he smelled the bacon.',
			author: 'Charles M. Russell'
		},
		{
			quote:
				"It ain't dying I'm talking about, it's living. I doubt it matters where you die, but it matters where you live.",
			author: 'Lonesome Dove (Gus McCrae)'
		}
	];

	// Reactive functions
	let quote = getRandomQuote();
	$: if ($navigating) {
		is_mobile_open = false; // Close mobile menu when navigation
	}
</script>

<header class="absolute inset-x-0 top-0 z-50">
	<nav class="mx-auto flex max-w-7xl items-center justify-between p-6 lg:px-8" aria-label="Global">
		<div class="flex lg:flex-1">
			<a href="/" class="-m-1.5 p-1.5">
				<span class="sr-only">{SITE_DATA.name}</span>
				<img
					width="40"
					height="40"
					src={SITE_DATA.logo.url}
					sizes="100vw"
					alt={SITE_DATA.logo.alt}
					class="object-contain"
				/>
			</a>
		</div>

		<div class="hidden lg:flex lg:gap-x-12">
			{#each SITE_DATA.routes as { id, url }}
				<Button href={url} variant="link" class="capitalize">{id}</Button>
			{/each}
		</div>
		<div class="flex space-x-4 lg:flex lg:flex-1 lg:justify-end">
			<Lightswitch />
			<!-- Mobile menu, show/hide based on menu open state. -->
			<div class="lg:hidden" role="dialog" aria-modal="true">
				<Sheet.Root bind:open={is_mobile_open} onOpenChange={() => (quote = getRandomQuote())}>
					<Sheet.Trigger asChild let:builder>
						<Button builders={[builder]} size="icon" variant="outline">
							<span class="sr-only">Open navigation menu</span>
							<MenuIcon class="h-6 w-6" /></Button
						>
					</Sheet.Trigger>
					<Sheet.Content side="right">
						<Sheet.Header>
							<Sheet.Title>Navigation</Sheet.Title>
							{#if quote}
								<Sheet.Description>
									<q>
										{quote.quote} ~
										{quote.author}
									</q>
								</Sheet.Description>
							{/if}
						</Sheet.Header>
						<Separator class="mt-4" />
						<div>
							<div class="space-y-2 py-6">
								<Button
									href="/"
									variant="link"
									class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7"
									>Home</Button
								>
								{#each SITE_DATA.routes as { id, url }}
									<Button
										href={url}
										variant="link"
										class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold capitalize leading-7"
										>{id}</Button
									>
								{/each}
							</div>
							<Separator />
							<div class="flex flex-col sm:flex-row sm:space-x-6">
								<Button variant="default" href="/donate" class="mt-4 w-full">Donate</Button>
								<Button variant="secondary" href="/watch" class="mt-4 w-full">Watch</Button>
							</div>
						</div>
					</Sheet.Content>
				</Sheet.Root>
			</div>
		</div>
	</nav>
</header>
