<script>
  export let className = '';

  const scrollToElem = (selector) => {
    const elem = document.querySelector(selector);
    if (!elem) return;

    let position = elem.getBoundingClientRect().top;
    let offset = position + window.pageYOffset - 50;
    console.log(position, window.pageYOffset, offset);

    window.scrollTo({
      top: offset,
      behavior: 'smooth'
    });
  };
</script>

<a href="#contact" 
  on:click|preventDefault={() => scrollToElem('#contact')} 
  class={className}  
>
  Contact Us
</a>

<style>
  .nav-link {
    color: var(--deep-blue);
		transition: .3s;
		font-size: 1.5rem;
		font-weight: 700;
  }
  .nav-link:hover {
    color: var(--med-slate);
		text-decoration: none;
  }
</style>