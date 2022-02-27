<script>
  import Input from '$lib/controls/Input.svelte';

  let name = '';
  let email = '';
  let phone = '';
  let message = '';

  const onInputChange = (event, field) => {
    let v = event.target.value;
    switch (field) {
      case 'name':
        name = v;
      case 'email':
        email = v;
      case 'phone':
        phone = v;
      case 'message':
        message = v;
    }
    console.log(name, email, phone, message);
  }
</script>

<div class="contact-banner">
  <div class="container">
    <div class="left">
      <h3>
        <span>Your project<br> begins here.</span>
        <strong>Request your free<br> estimate today!</strong>
      </h3>
    </div>
    <div class="right">
      <form>
        <div class="top-row">
          <Input fieldName="name" label="Name" change={(e) => {onInputChange(e, 'name')}} />
          <Input fieldName="phone" label="Phone" type="phone" change={(e) => onInputChange(e, 'phone')} />
          <Input fieldName="email" label="Email" type="email" change={(e) => onInputChange(e, 'email')} />
        </div>
        <div class="btm-row">
          <Input fieldName="message" label="Message" change={(e) => onInputChange(e, 'message')} />
        </div>
      </form>
    </div>
  </div>
</div>

<style>
  .contact-banner {
    background: var(--deep-blue);
    /* padding: 1rem 0; */
  }
  .contact-banner .container {
    display: grid;
    grid-template-columns: 1fr 3fr;
    align-items: center;
  }
  .contact-banner h3 {
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  .contact-banner h3 strong {
    color: var(--mustard);
  }

  .top-row {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
  }
  .btm-row {
    display: grid;
    grid-template-columns: 2fr 1fr;
  }

</style>