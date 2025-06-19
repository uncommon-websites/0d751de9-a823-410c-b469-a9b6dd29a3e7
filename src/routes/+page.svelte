<script lang="ts">
	// Components
	import UseCases from "$lib/components/layout/UseCases.svelte";
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import SidebarNavigationHero from "$lib/components/layout/hero-sections/SidebarNavigationHero.svelte";
</script>

<SidebarNavigationHero
	title="Automate workflows with AI agents"
	subtitle="Deploy critical physical infrastructure faster with AI-native tooling and agentic automation designed for the built world."
	navigationItems={[
		{ label: "AI + Infrastructure", active: true },
		{ label: "Site Selection" },
		{ label: "Due Diligence" },
		{ label: "Permitting" },
		{ label: "Utilities" }
	]}
	productOptions={[
		{
			icon: "🏗️",
			title: "Build Agents for infrastructure",
			subtitle: "Automate development workflows",
			href: "/agents"
		},
		{
			icon: "📊",
			title: "Analytics Platform",
			subtitle: "Real-time project insights",
			href: "/analytics"
		}
	]}
	pickYourProductLabel="Pick your solution"
/>
<LogoScroller 
	label="Trusted by industry leaders"
	logoUrls={[
		'https://logo.clearbit.com/digitalrealty.com',
		'https://logo.clearbit.com/equinix.com',
		'https://logo.clearbit.com/cbre.com',
		'https://logo.clearbit.com/jll.com',
		'https://logo.clearbit.com/brookfieldproperties.com'
	]}
/>

<Summary
	title="What we do"
	text="Our technology delivers measurable results through secure, adaptable solutions that directly increase productivity and drive growth."
/>

<img src="/placeholder.jpg" alt="Testimonials Image" />

<Features
	title="Features"
	subtitle="Some features"
	features={[
		{
			title: "Streamlined Workflows",
			description:
				"Automate repetitive tasks and connect systems to improve productivity with our industry-leading 87% time savings."
		},
		{
			title: "Data Analysis",
			description:
				"Extract meaningful insights from your data with powerful analytical tools backed by proprietary AI algorithms that are 3x more accurate than competitors."
		},
		{
			title: "Secure Collaboration",
			description:
				"Work together seamlessly while maintaining strict data privacy standards with our zero-knowledge architecture and military-grade encryption."
		}
	]}
/>

<UseCases
	title="Use Cases"
	subtitle="Real-world applications for your business needs"
	useCases={[
		{
			title: "Streamlined Workflows",
			description:
				"Automate repetitive tasks and connect systems to improve productivity with our industry-leading 87% time savings.",
			image:
				"/uploaded/1750374481323-cphmcns.jpeg",
			link: {
				href: "/use-cases/workflows",
				label: "Learn more"
			}
		},
		{
			title: "Data Analysis",
			description:
				"Extract meaningful insights from your data with powerful analytical tools backed by proprietary AI algorithms that are 3x more accurate than competitors.",
			image:
				"/uploaded/1750374481323-i0cbakw.jpeg",
			link: {
				href: "/use-cases/data-analysis",
				label: "Explore analytics"
			}
		},
		{
			title: "Secure Collaboration",
			description:
				"Work together seamlessly while maintaining strict data privacy standards with our zero-knowledge architecture and military-grade encryption.",
			image:
				"/uploaded/1750374481324-nzttrr3.png",
			link: {
				href: "/use-cases/collaboration",
				label: "See security features"
			}
		}
	]}
/>

<AboutTeaser />
<CallToAction 
	title="Have a use case in mind?"
	subtitle="Let's talk"
	description="You'll hear back in less than 24 hours"
	imageSrcs={[
		"/uploaded/1750375637744-7o0atq9.jpeg",
		"/uploaded/1750375637744-8f4iajq.jpeg"
	]}
	callsToAction={[
		{
			href: "/contact",
			label: "Book a demo",
			variant: "primary"
		}
	]}
/>
