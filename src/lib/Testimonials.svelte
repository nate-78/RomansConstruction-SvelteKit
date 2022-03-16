<script>
  import Slider from "$lib/controls/slider/Slider.svelte";
  import Slide from '$lib/controls/slider/Slide.svelte';
  import Testimonial from "./Testimonial.svelte";
</script>

<div class="testimonials-wrap">
  <div class="container">
    <div class="test-wrap">
      <div class="left">
        <p class="pre-heading">
          Testimonials
        </p>
        <h2 class="mt-1">
          Don't just take<br>
          <b>our word for it...</b>
        </h2>
        <p>
          We know the importance of getting business through 
          word of mouth. Here are a few examples of what our 
          customers have to say.
        </p>
      </div>
      <div class="right">
        <Slider numSlides={3}>
          <Slide>
            <Testimonial name="Skip Smith" location="Decatur, Alabama">
              <p>
                Simply an outstanding work ethic. I can't say enough about the level of 
                integrity from the guys at Roman's Construction. I could tell they actually
                cared about what I needed.
              </p>
            </Testimonial>
          </Slide>
          <Slide>
            <Testimonial name="Lindsay Owens" location="Decatur, Alabama">
              <p>
                Everyone on the crew seemed so friendly.  And I was really impressed 
                with how quickly they were able to finish our project.  I'd definitely 
                use them again.
              </p>
            </Testimonial>
          </Slide>
          <Slide>
            <Testimonial name="Josh Walker" location="Decatur, Alabama">
              <p>
                A friend recommended Roman's Construction when we needed a new roof,
                and I'm really glad we used them.  They made the process so easy.
              </p>
            </Testimonial>
          </Slide>
        </Slider>
      </div>
    </div>
  </div>
</div>

<style>
  .testimonials-wrap {
    background-image: url('images/blue-granite.webp');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    padding: 50px 0;
  }
  .test-wrap {
    display: grid;
    grid-gap: 25px;
    grid-template-columns: 40% 60%;
    align-items: center;
    text-align: center;
    padding: 0 35px;
  }
  .test-wrap h2, .test-wrap {
    color: white;
  }
  .test-wrap h2 {
    margin-bottom: 1rem;
  }
  p.pre-heading {
    color: var(--pale-blue);
  }
</style>