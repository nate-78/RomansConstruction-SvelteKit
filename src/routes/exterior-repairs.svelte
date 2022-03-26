<script>
  import BannerInner from '$lib/BannerInner.svelte';
	import ContactBanner from '$lib/ContactBanner.svelte';
	import ServiceContent from '$lib/ServiceContent.svelte';
	import Testimonials from '$lib/Testimonials.svelte';
	import Gallery from '$lib/Gallery.svelte';
</script>

<svelte:head>
	<title>Exterior Repairs | Roman's Construction</title>
</svelte:head>

<div>
  <BannerInner bannerImg="images/clouds.webp"
		bldgImg="images/house.webp"
		titleTopLine="Committed to excellence "
		titleBtmLine="from top to bottom."
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
		smImg="images/services/exterior.webp"
		smImgAlt="exterior repair"
		preHeading="Residential"
		heading="Restoring your home's beauty."
		svcList={[]}
	>
		<p>
			Siding can serve several purposes for your home or business: provide 
			insulation, protect your property, and add curb appeal. We 
			can ensure that your exteriors are beautiful and durable. We've been 
			trusted by our clients for many 
			years to provide some of the highest quality siding options. 
		</p>
	</ServiceContent>

	<Testimonials />
	<Gallery />
</div>
