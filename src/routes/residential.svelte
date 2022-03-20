<script>
  import BannerInner from '$lib/BannerInner.svelte';
	import ContactBanner from '$lib/ContactBanner.svelte';
	import ServiceContent from '$lib/ServiceContent.svelte';
	import Testimonials from '$lib/Testimonials.svelte';
	import Gallery from '$lib/Gallery.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<div>
  <BannerInner bannerImg="images/clouds.webp"
		bldgImg="images/house.webp"
		titleTopLine="Committed to excellence "
		titleBtmLine="from start to finish."
	>
		<p>
			We take pride in offering excellent service and quality products 
			to our clients. We are here for one purpose &ndash; to serve you.
		</p>
	</BannerInner>
	<ContactBanner />
	<ServiceContent
		lgImg="images/neighborhood.webp"
		lgImgAlt="neighborhood"
		smImg="images/shingles.webp"
		smImgAlt="shingles"
		preHeading="Residential"
		heading="Helping your home stand the test of time."
		svcList={['roof repair', 'roof replacement', 'exterior repair']}
	>
		<p>
			Homes can develop a lot of wear and tear over time, and yours is no 
			exception. Contact us today to see how we can revitalize your home.
		</p>
	</ServiceContent>
	<Testimonials />
	<Gallery />
</div>
