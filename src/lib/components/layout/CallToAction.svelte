<!--
    @component
    A call-to-action component that attracts attention and encourages user engagement.

    Usage:
    ```html
    <CallToAction
      title="Get started today"
      subtitle="Join now"
      description="Ready to experience the difference? Join our community of satisfied customers and see how our solution can transform your workflow."
      image="/path/to/image.jpg"
      callsToAction={[
        {
          href: "/get-started",
          label: "Get Started",
          variant: "primary"
        },
        {
          href: "/contact",
          label: "Talk to Sales",
          variant: "secondary"
        }
      ]}
    />
    ```

    Props:
    - `title`: The main heading text (string)
    - `subtitle`: Secondary heading text (string)
    - `description`: Detailed information about the offer (string)
    - `callsToAction`: Array of CTA objects with href, label, and optional variant properties (CTA[])
    - `imageSrc`: portrait of the company's customer smiling at the camera.
-->

<script lang="ts">
	// Types
	import type { ComponentProps } from "svelte";

	// Components
	import Button from "../ui/Button.svelte";
	import AnimateText from "../animation/AnimateText.svelte";
	import { cta } from "$lib/navigation";

	// Types
	type CTA = {
		href: string;
		label: string;
		variant?: ComponentProps<typeof Button>["variant"];
	};

	// Props
	const {
		title = "Get started today",
		subtitle = "Join now",
		description = "Ready to experience the difference? Join our community of satisfied customers and see how our solution can transform your workflow. ",
		imageSrc = "https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80",
		callsToAction = [cta],
		...rest
	}: {
		title?: string;
		subtitle?: string;
		description?: string;
		imageSrc?: string;
		callsToAction?: CTA[];
	} = $props();
</script>

<div class="" {...rest}>
	<section class="section-px section-py container mx-auto">
		<div
			class="bg-gray-900 text-white grid content-start items-center justify-between gap-0 rounded-2xl overflow-hidden lg:grid-cols-[1fr_1fr] min-h-[500px]"
		>
			<div class="flex flex-col justify-center gap-8 p-12 lg:p-16">
				<div class="flex flex-col gap-4">
					<h2 class="text-4xl lg:text-5xl font-medium leading-tight">
						<AnimateText text={title} />
					</h2>
					<h3 class="text-2xl lg:text-3xl font-light text-gray-300">
						<AnimateText text={subtitle} />
					</h3>
				</div>
				<div class="flex flex-col gap-6">
					<p class="text-sm text-gray-400 leading-relaxed">
						{description}
					</p>
					<div class="flex flex-col sm:flex-row gap-3">
						{#each callsToAction as cta}
							<Button 
								class="bg-white text-gray-900 hover:bg-gray-100 border-0 px-6 py-3 rounded-full font-medium" 
								href={cta.href} 
								variant="secondary"
							>
								{cta.label}
							</Button>
						{/each}
					</div>
				</div>
			</div>
			<div class="relative h-full min-h-[400px] lg:min-h-[500px]">
				<img
					src={imageSrc}
					alt="Professional working with laptop"
					class="absolute inset-0 w-full h-full object-cover"
				/>
			</div>
		</div>
	</section>
</div>
