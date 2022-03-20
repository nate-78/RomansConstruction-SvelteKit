<script>
  import BannerInner from '$lib/BannerInner.svelte';
	import ContactBanner from '$lib/ContactBanner.svelte';
	import AboutContent from '$lib/AboutContent.svelte';
	import Testimonials from '$lib/Testimonials.svelte';
	import Gallery from '$lib/Gallery.svelte';
</script>

<svelte:head>
	<title>About | Roman's Construction</title>
</svelte:head>

<div>
  <BannerInner bannerImg="images/clouds.webp"
		bldgImg="images/house.webp"
		titleTopLine="Quality and dependability "
		titleBtmLine="you can count on."
	>
		<p>
			From small buildings to shopping centers, single story or 
			multi story, we've got you covered.
		</p>
	</BannerInner>

	<ContactBanner />

	<AboutContent
		preheading="Who We Are"
		headingLight="We've got "
		headingBold="you covered."
		img="images/neighborhood.webp"
		imgAlt="neighborhood"
	>
		<p slot="topSlot">
			We earn trust the old-fashioned way - by operating with integrity, open 
			communication, responsiveness, and getting things done right.  We 
			ensure total transparency and always operate with the understanding 
			that your best interest is also ours.
		</p>
		<p slot="btmSlot">
			We’re a family-owned business based in Decatur, Alabama. We are committed to providing 
			service focused on quality, value and customer satisfaction. We love what we do—and it shows.
		</p>
	</AboutContent>

	<Testimonials />
	<Gallery />
</div>
