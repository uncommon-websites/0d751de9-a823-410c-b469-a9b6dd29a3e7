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
				"https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2940&q=80",
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
				"https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2488&q=80",
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
				"https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2940&q=80",
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
	imageSrc="/uploaded/1750374414743-qfjjohb.png"
	callsToAction={[
		{
			href: "/contact",
			label: "Book a demo",
			variant: "primary"
		}
	]}
/>
