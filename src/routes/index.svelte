<script context="module">
	export const prerender = true;
</script>

<script>
	import Banner from '$lib/Banner.svelte';
	import ContactBanner from '$lib/ContactBanner.svelte';
	import Services from '$lib/home/Services.svelte';
	import Testimonials from '$lib/Testimonials.svelte';
	import Gallery from '$lib/Gallery.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<div>
	<Banner bannerImg="images/banner-home.webp"
		titleTopLine="Committed to excellence "
		titleBtmLine="from start to finish."
		btnLink="/#testimonials"
		btnText="Learn More"
	>
		<p>
			We take pride in offering excellent service and quality products 
			to our clients. We are here for one purpose &ndash; to serve you.
		</p>
	</Banner>
	<ContactBanner />
	<Services />
	<Testimonials />
	<Gallery />
</div>

<style>

</style>
