<script>
	import WelcomeSection from '../lib/components/WelcomeSection.svelte';
	import ProjectsSection from '../lib/components/ProjectsSection.svelte';
	import ReviewsSection from '../lib/components/ReviewsSection.svelte';
	import ProjectRequestSection from '../lib/components/ProjectRequestSection.svelte';
	import FaqSection from '../lib/components/FaqSection.svelte';
</script>

<div class="homepage">
	<WelcomeSection />
	<ProjectsSection />
	<ReviewsSection />
	<ProjectRequestSection />
	<FaqSection />
</div>

<style>
	.homepage {
		display: flex;
		flex-direction: column;
		gap: var(--size-xxl);

		overflow: hidden;
	}
</style>
