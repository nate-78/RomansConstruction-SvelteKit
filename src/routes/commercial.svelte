<script>
  import BannerInner from '$lib/BannerInner.svelte';
	import ContactBanner from '$lib/ContactBanner.svelte';
	import ServiceContent from '$lib/ServiceContent.svelte';
	import Testimonials from '$lib/Testimonials.svelte';
	import Gallery from '$lib/Gallery.svelte';
</script>

<svelte:head>
	<title>Commercial Roofing | Roman's Construction</title>
</svelte:head>

<div>
  <BannerInner bannerImg="images/clouds.webp"
		bldgImg="images/office.webp"
		titleTopLine="Because your business "
		titleBtmLine="deserves the best."
	>
		<p>
			From small buildings to shopping centers, single story 
      or multi story, we've got you covered.
		</p>
	</BannerInner>
	<ContactBanner />
	<ServiceContent
		lgImg="images/industrial-park.webp"
		lgImgAlt="industrial park"
		smImg="images/hardhat.webp"
		smImgAlt="hardhat"
		preHeading="Commercial"
		heading="Your business is our business."
		svcList={['roof repair', 'roof replacement', 'exterior repair']}
	>
		<p>
			Our contractors are ready to work with you to protect your business 
      while keeping your daily operations moving steadily.
		</p>
	</ServiceContent>
	<Testimonials />
	<Gallery />
</div>
