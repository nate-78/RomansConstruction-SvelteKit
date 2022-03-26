<footer>
  <div class="container">
    <div class="left">
      <div class="logo-sm">
        <img src="images/logo-narrows.webp" alt="roman's construction" />
      </div>
      <div class="address">
        <b>Roman's Construction</b><br />
        3506 Hooper Lane<br />
        Decatur, AL 35603<br />
        <a href="tel:2565666994">(256) 566-6994</a>
      </div>
    </div>
    <div class="right">
      <nav>
        <ul>
          <li>
            <a href="/" sveltekit:prefetch>Home</a>
          </li>
          <li>
            <a href="/about" sveltekit:prefetch>About Us</a>
          </li>
          <li>
            <a href="/#services" sveltekit:prefetch>Services</a>
          </li>
          <li>
            <a href="/gallery" sveltekit:prefetch>Gallery</a>
          </li>
          <li>
            <a href="/#contact" sveltekit:prefetch>Contact Us</a>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</footer>

<style>
  footer {
    background: var(--deep-blue);
    padding: 30px 0;
  }
  footer * {
    color: white;
  }

  footer .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  footer .left {
    display: flex;
    align-items: center;
  }
  footer .left > div:first-child {
    margin-right: 1rem;
  }

  footer .left .address {
    font-size: .9rem;
  }

  footer .left .address b {
    text-transform: uppercase;
  }

  footer .right nav ul {
    list-style: none;
    padding: 0;
    display: flex;
  }
  footer .right nav ul li {
    margin-left: 1.5rem;
    text-transform: uppercase;
    font-family: 'Roboto Condensed', sans-serif;
  }

  img {
    width: 80px;
  }

  @media (max-width: 800px) {
    footer .container {
      flex-direction: column;
    }
    footer .left {
      margin-bottom: 1rem;
    }
  }
  @media (max-width: 525px) {
    footer .right nav ul {
      flex-wrap: wrap;
      justify-content: center;
    }
  }
</style>