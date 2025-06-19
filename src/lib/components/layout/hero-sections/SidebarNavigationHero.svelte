<!--
@component SidebarNavigationHero

This component displays a hero section with a left sidebar navigation and product selection,
inspired by the V7 layout with clean, minimalist design.
-->

<script lang="ts">
	// Components
	import AnimateText from "$lib/components/animation/AnimateText.svelte";
	import Button from "$lib/components/ui/Button.svelte";

	// Types
	type NavigationItem = {
		label: string;
		active?: boolean;
	};

	type ProductOption = {
		icon: string;
		title: string;
		subtitle: string;
		href?: string;
	};

	type Props = {
		title: string;
		subtitle?: string;
		navigationItems?: NavigationItem[];
		productOptions?: ProductOption[];
		pickYourProductLabel?: string;
	};

	let {
		title,
		subtitle,
		navigationItems = [
			{ label: "AI Agents", active: true },
			{ label: "Site Selection" },
			{ label: "Due Diligence" },
			{ label: "Permitting" },
			{ label: "Utilities" }
		],
		productOptions = [
			{
				icon: "🏗️",
				title: "Build Agents for infrastructure",
				subtitle: "Automate development workflows",
				href: "/agents"
			},
			{
				icon: "📊",
				title: "Analytics Dashboard",
				subtitle: "Real-time project insights",
				href: "/analytics"
			}
		],
		pickYourProductLabel = "Pick your solution",
		...rest
	}: Props = $props();
</script>

<div class="min-h-[calc(100vh-var(--nav-height))] bg-white" {...rest}>
	<div class="flex">
		<!-- Left Sidebar Navigation -->
		<div class="w-64 bg-gray-50 min-h-[calc(100vh-var(--nav-height))] border-r border-gray-200">
			<div class="p-6">
				<nav class="space-y-2">
					{#each navigationItems as item}
						<div 
							class="flex items-center px-3 py-2 text-sm font-medium rounded-md transition-colors duration-200 {item.active ? 'bg-black text-white' : 'text-gray-600 hover:bg-gray-100'}"
						>
							<span class="w-2 h-2 rounded-full mr-3 {item.active ? 'bg-white' : 'bg-gray-400'}"></span>
							{item.label}
						</div>
					{/each}
				</nav>
			</div>
		</div>

		<!-- Main Content Area -->
		<div class="flex-1 flex flex-col">
			<!-- Hero Content -->
			<div class="flex-1 px-12 py-16">
				<div class="max-w-4xl">
					<!-- Main Headline -->
					<div class="mb-12" data-enter-container>
						<h1 
							class="text-5xl lg:text-6xl font-bold text-gray-900 mb-6 leading-tight" 
							data-enter
						>
							<AnimateText text={title} />
						</h1>
						
						{#if subtitle}
							<p 
								class="text-xl text-gray-600 max-w-2xl leading-relaxed" 
								data-enter
							>
								{subtitle}
							</p>
						{/if}
					</div>

					<!-- Product Selection -->
					<div class="mb-8" data-enter>
						<p class="text-sm text-gray-500 mb-4 font-medium">
							{pickYourProductLabel} →
						</p>
						
						<div class="space-y-3">
							{#each productOptions as option}
								<a 
									href={option.href || '#'}
									class="group flex items-center p-4 border border-gray-200 rounded-lg hover:border-gray-300 hover:shadow-sm transition-all duration-200 bg-white"
								>
									<div class="flex items-center justify-center w-10 h-10 rounded-lg bg-gray-100 mr-4 text-lg group-hover:bg-gray-200 transition-colors duration-200">
										{option.icon}
									</div>
									<div class="flex-1">
										<div class="font-semibold text-gray-900 mb-1">
											{option.title}
										</div>
										<div class="text-sm text-gray-600">
											{option.subtitle}
										</div>
									</div>
									<div class="text-gray-400 group-hover:text-gray-600 transition-colors duration-200">
										<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
											<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
										</svg>
									</div>
								</a>
							{/each}
						</div>
					</div>
				</div>
			</div>

			<!-- Bottom Blurred Interface Preview -->
			<div class="relative h-64 overflow-hidden border-t border-gray-200">
				<div class="absolute inset-0 bg-gradient-to-t from-white via-white/80 to-transparent z-10"></div>
				<div class="p-6 opacity-40 blur-sm">
					<div class="bg-gray-50 rounded-lg p-4">
						<div class="flex items-center justify-between mb-4">
							<div class="text-sm font-medium text-gray-600">Project Status</div>
							<div class="text-xs text-gray-500">Real-time updates</div>
						</div>
						<div class="space-y-3">
							<div class="flex items-center justify-between p-3 bg-white rounded border">
								<div class="flex items-center space-x-3">
									<div class="w-2 h-2 bg-green-500 rounded-full"></div>
									<span class="text-sm">Site Analysis</span>
								</div>
								<span class="text-xs text-green-600 font-medium">Complete</span>
							</div>
							<div class="flex items-center justify-between p-3 bg-white rounded border">
								<div class="flex items-center space-x-3">
									<div class="w-2 h-2 bg-yellow-500 rounded-full"></div>
									<span class="text-sm">Permit Review</span>
								</div>
								<span class="text-xs text-yellow-600 font-medium">In Progress</span>
							</div>
							<div class="flex items-center justify-between p-3 bg-white rounded border">
								<div class="flex items-center space-x-3">
									<div class="w-2 h-2 bg-gray-300 rounded-full"></div>
									<span class="text-sm">Utility Coordination</span>
								</div>
								<span class="text-xs text-gray-500 font-medium">Pending</span>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>