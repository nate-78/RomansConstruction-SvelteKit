<script context="module">
	export const prerender = true;
</script>

<script>
	import Banner from '$lib/Banner.svelte';
	import ContactBanner from '$lib/ContactBanner.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<Banner bannerImg="images/banner-home.webp"
		titleTopLine="Committed to excellence "
		titleBtmLine="from start to finish."
		btnLink="/about"
		btnText="Learn More"
	>
		<p>
			We take pride in offering excellent service and quality products 
			to our clients. We are here for one purpose &ndash; to serve you.
		</p>
	</Banner>
	<ContactBanner />
	
</section>

<style>
	/* section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	} */

</style>
