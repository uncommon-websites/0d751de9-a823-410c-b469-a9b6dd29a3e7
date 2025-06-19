<script lang="ts">
	import Card from "../ui/Card.svelte";

	// Types
	import type { ComponentType } from "svelte";
	
	type Feature = {
		title: string;
		description: string;
		icon?: ComponentType;
		iconClass?: string;
		imageSrc?: string;
		imageAspect?: "16/9" | "9/16";
		link?: {
			href: string;
			label: string;
		};
	};

	// Components
	import SectionHeader from "./SectionHeader.svelte";

	// Props
	const {
		title,
		subtitle,
		features = [],
		...rest
	}: { title: string; subtitle: string; features: Feature[] } = $props();

	let featureCountClass = $derived(
		features.length <= 6 ? `feature-count-${features.length}` : "feature-count-many"
	);
</script>

<section class="features-section" {...rest}>
	<div class="gradient-background">
		<div class="section-px section-py container mx-auto">
			<div class="header-container">
				<SectionHeader {title} {subtitle} />
			</div>

			<div class="features-showcase">
				<div class="code-window">
					<div class="window-header">
						<div class="window-controls">
							<span class="control red"></span>
							<span class="control yellow"></span>
							<span class="control green"></span>
						</div>
						<div class="window-title">Features</div>
					</div>
					<div class="code-content">
						{#each features as feature, index}
							<div class="feature-line">
								<span class="line-number">{index + 1}</span>
								<span class="feature-code">
									<span class="keyword">feature</span>
									<span class="function-name">{feature.title.replace(/\s+/g, '')}</span>
									<span class="bracket">(</span>
									<span class="string">"{feature.description}"</span>
									<span class="bracket">)</span>
									<span class="semicolon">;</span>
								</span>
							</div>
						{/each}
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<!--
@component
A feature grid section that displays a list of features with titles and descriptions.
Never use title case, always sentence case.

Make the feature descriptions one short sentence that clearly articulates the feature.

Usage:
```html
<script>
  import IconStar from '~icons/lucide/star';
</script>

<FeatureSection
  title="Section Title"
  subtitle="Section Subtitle"
  features={[
    {
      title: "Feature Title",
      description: "Feature description text",
      icon: IconStar, // optional - Lucide icon component
      imageSrc: "https://example.com/image.jpg", // optional - image URL (use either icon OR imageSrc)
      link: { href: "/optional-link", label: "Learn more" } // optional
    }
    // more features...
  ]}
/>
```
-->

<style>
	.features-section {
		position: relative;
		overflow: hidden;
	}

	.gradient-background {
		background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 25%, #dc2626 50%, #7c3aed 75%, #6366f1 100%);
		padding: 4rem 0;
		min-height: 80vh;
		display: flex;
		align-items: center;
	}

	.header-container {
		text-align: center;
		margin-bottom: 3rem;
	}

	.header-container :global(h2) {
		color: white;
		font-size: 3rem;
		font-weight: 700;
		margin-bottom: 1rem;
		text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
	}

	.header-container :global(p) {
		color: rgba(255, 255, 255, 0.9);
		font-size: 1.25rem;
		text-shadow: 0 1px 2px rgba(0, 0, 0, 0.2);
	}

	.features-showcase {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.code-window {
		background: #1e1e1e;
		border-radius: 12px;
		box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
		overflow: hidden;
		max-width: 800px;
		width: 100%;
		margin: 0 auto;
	}

	.window-header {
		background: #2d2d2d;
		padding: 12px 16px;
		display: flex;
		align-items: center;
		border-bottom: 1px solid #404040;
	}

	.window-controls {
		display: flex;
		gap: 8px;
		margin-right: 16px;
	}

	.control {
		width: 12px;
		height: 12px;
		border-radius: 50%;
	}

	.control.red {
		background: #ff5f56;
	}

	.control.yellow {
		background: #ffbd2e;
	}

	.control.green {
		background: #27ca3f;
	}

	.window-title {
		color: #cccccc;
		font-size: 14px;
		font-family: 'SF Mono', Monaco, 'Cascadia Code', 'Roboto Mono', Consolas, 'Courier New', monospace;
	}

	.code-content {
		padding: 24px;
		font-family: 'SF Mono', Monaco, 'Cascadia Code', 'Roboto Mono', Consolas, 'Courier New', monospace;
		font-size: 16px;
		line-height: 1.6;
		background: #1e1e1e;
	}

	.feature-line {
		display: flex;
		align-items: center;
		margin-bottom: 8px;
		padding: 4px 0;
	}

	.line-number {
		color: #6e7681;
		width: 40px;
		text-align: right;
		margin-right: 24px;
		font-size: 14px;
		user-select: none;
	}

	.feature-code {
		display: flex;
		align-items: center;
		gap: 8px;
	}

	.keyword {
		color: #ff7b72;
		font-weight: 600;
	}

	.function-name {
		color: #d2a8ff;
		font-weight: 500;
	}

	.bracket {
		color: #79c0ff;
	}

	.string {
		color: #a5d6ff;
	}

	.semicolon {
		color: #f85149;
	}

	/* Mobile responsiveness */
	@media (max-width: 768px) {
		.gradient-background {
			padding: 2rem 0;
			min-height: 60vh;
		}

		.header-container :global(h2) {
			font-size: 2rem;
		}

		.header-container :global(p) {
			font-size: 1rem;
		}

		.code-window {
			margin: 0 1rem;
		}

		.code-content {
			padding: 16px;
			font-size: 14px;
		}

		.line-number {
			width: 30px;
			margin-right: 16px;
		}

		.feature-code {
			gap: 4px;
			flex-wrap: wrap;
		}
	}

	/* Hover effects */
	.feature-line {
		transition: all 0.2s ease;
		border-radius: 4px;
		padding: 8px 4px;
	}

	.feature-line:hover {
		background: rgba(255, 255, 255, 0.05);
		transform: translateX(4px);
	}

	/* Animation for code appearance */
	.feature-line {
		opacity: 0;
		animation: fadeInUp 0.6s ease forwards;
	}

	.feature-line:nth-child(1) { animation-delay: 0.1s; }
	.feature-line:nth-child(2) { animation-delay: 0.2s; }
	.feature-line:nth-child(3) { animation-delay: 0.3s; }
	.feature-line:nth-child(4) { animation-delay: 0.4s; }
	.feature-line:nth-child(5) { animation-delay: 0.5s; }

	@keyframes fadeInUp {
		from {
			opacity: 0;
			transform: translateY(20px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}
</style>
