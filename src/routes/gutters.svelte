<script>
  import BannerInner from '$lib/BannerInner.svelte';
	import ContactBanner from '$lib/ContactBanner.svelte';
	import ServiceContent from '$lib/ServiceContent.svelte';
	import Testimonials from '$lib/Testimonials.svelte';
	import Gallery from '$lib/Gallery.svelte';
</script>

<svelte:head>
	<title>Gutters | Roman's Construction</title>
</svelte:head>

<div>
  <BannerInner bannerImg="images/clouds.webp"
		bldgImg="images/svc-gutters.webp"
		titleTopLine="Committed to excellence "
		titleBtmLine="from top to bottom."
	>
		<p>
			We take pride in the quality of our work. We're dependable, 
			affordable, and committed to excellent service.
		</p>
	</BannerInner>

	<ContactBanner />

	<ServiceContent
		lgImg="images/neighborhood.webp"
		lgImgAlt="neighborhood"
		smImg="images/services/gutters.webp"
		smImgAlt="gutters"
		preHeading="Residential"
		heading="Keeping your home and yard in optimal condition."
		svcList={[]}
	>
		<p>
			Not only are gutters an attractive addition to your home, but 
			they help keep your yard healthy and your home protected. Call 
			us today to get an estimate.
		</p>
	</ServiceContent>

	<Testimonials />
	<Gallery />
</div>
