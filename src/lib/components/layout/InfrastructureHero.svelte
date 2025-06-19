<script lang="ts">
	type Props = {
		title?: string;
		subtitle?: string;
		description?: string;
		buttonText?: string;
		buttonHref?: string;
		backgroundImage?: string;
	};

	let {
		title = "Heavy machines. Strong bodies, smart minds.",
		subtitle = "Infrastructure built right",
		description = "We pioneer the development of AI-native tooling for heavy machinery in construction, energy, and infrastructure industries.",
		buttonText = "Learn more",
		buttonHref = "/about",
		backgroundImage = "/generated/image-a-group-of-construction-workers-wearing-.webp"
	}: Props = $props();
</script>

<section class="infrastructure-hero">
	<div class="hero-container">
		<div class="hero-content">
			<div class="text-content">
				<h2 class="hero-title">{title}</h2>
				<div class="hero-details">
					<p class="hero-description">{description}</p>
					<a href={buttonHref} class="hero-button">{buttonText}</a>
				</div>
			</div>
		</div>
		<div class="hero-image">
			<img src={backgroundImage} alt="Infrastructure workers" />
		</div>
	</div>
</section>

<style>
	.infrastructure-hero {
		position: relative;
		background: #2a2a2a;
		color: white;
		overflow: hidden;
		min-height: 600px;
		display: flex;
		align-items: center;
	}

	.hero-container {
		position: relative;
		width: 100%;
		max-width: 1400px;
		margin: 0 auto;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 4rem;
		align-items: center;
		padding: 4rem 2rem;
	}

	.hero-content {
		z-index: 2;
		position: relative;
	}

	.text-content {
		max-width: 500px;
	}

	.hero-title {
		font-size: clamp(2.5rem, 5vw, 4rem);
		font-weight: 300;
		line-height: 1.1;
		margin: 0 0 2rem 0;
		letter-spacing: -0.02em;
	}

	.hero-details {
		display: flex;
		flex-direction: column;
		gap: 2rem;
		align-items: flex-start;
	}

	.hero-description {
		font-size: 1.1rem;
		line-height: 1.6;
		color: #b0b0b0;
		margin: 0;
		max-width: 400px;
	}

	.hero-button {
		display: inline-flex;
		align-items: center;
		padding: 0.75rem 1.5rem;
		background: rgba(255, 255, 255, 0.1);
		border: 1px solid rgba(255, 255, 255, 0.2);
		color: white;
		text-decoration: none;
		border-radius: 6px;
		font-weight: 500;
		transition: all 0.3s ease;
		backdrop-filter: blur(10px);
	}

	.hero-button:hover {
		background: rgba(255, 255, 255, 0.15);
		border-color: rgba(255, 255, 255, 0.3);
		transform: translateY(-1px);
	}

	.hero-image {
		position: relative;
		height: 500px;
		border-radius: 12px;
		overflow: hidden;
	}

	.hero-image img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		object-position: center;
	}

	@media (max-width: 768px) {
		.hero-container {
			grid-template-columns: 1fr;
			gap: 2rem;
			padding: 2rem 1rem;
			text-align: center;
		}

		.hero-image {
			height: 300px;
		}

		.text-content {
			max-width: none;
		}

		.hero-title {
			font-size: 2.5rem;
		}

		.hero-details {
			align-items: center;
		}
	}
</style>