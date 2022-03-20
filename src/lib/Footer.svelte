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
            <a href="/">Home</a>
          </li>
          <!-- <li>
            <a href="/about">About</a>
          </li> -->
          <li>
            <a href="/#services">Services</a>
          </li>
          <li>
            <a href="/gallery">Gallery</a>
          </li>
          <li>
            <a href="/#contact">Contact Us</a>
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
</style>