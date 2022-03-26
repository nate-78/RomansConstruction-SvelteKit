<script>
  import Input from '$lib/controls/Input.svelte';
  import Button from '$lib/controls/Button.svelte';

  let name = '';
  let email = '';
  let phone = '';
  let message = '';

  let showSubmitMsg = false;
  let successMessage = "Thank you for your message. We'll be in touch with you shortly.";
  let errorMsg = "";

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

  const submitForm = (event) => {
    event.preventDefault();
    console.log('got here');
    let data = new FormData(event.target);
    fetch(event.target.action, {
      method: 'POST',
      body: data,
      headers: {
        'Accept': 'application/json'
      }
    }).then(response => {
      if (response.ok) {
        showSubmitMsg = true;
        errorMsg = "";
      } else {
        response.json().then(data => {
          if (Object.hasOwn(data, 'errors')) {
            errorMsg = data["errors"].map(error => error["message"]).join(", ")
          } else {
            errorMsg = "Oops! There was a problem submitting your form."
          }
        });
      }
    });
  };
</script>

<div class="contact-banner" id="contact">
  <div class="container">
    <div class="left">
      <h3>
        <span>Your project<br> begins here.</span>
        <strong>Request your free<br> estimate today!</strong>
      </h3>
    </div>
    <div class="right">
      {#if !showSubmitMsg}
        <form on:submit={submitForm} action="https://formspree.io/f/xzboazjb">
          <div class="top-row">
            <Input fieldName="name" label="Name" change={(e) => {onInputChange(e, 'name')}} required={true} />
            <Input fieldName="phone" label="Phone" type="phone" change={(e) => onInputChange(e, 'phone')} />
            <Input fieldName="email" label="Email" type="email" change={(e) => onInputChange(e, 'email')} required={true} />
          </div>
          <div class="btm-row">
            <Input fieldName="message" label="Message" change={(e) => onInputChange(e, 'message')} />
            <Button isSubmitBtn={true} className="no-margin tall" text="Submit Your Request" hasWhiteText={true} />
          </div>
          {#if errorMsg != ""}
            <div class="row">
              <div class="col">
                <p class="error">
                  {errorMsg}
                </p>
              </div>
            </div>
          {/if}
        </form>
      {:else}
        <div class="center">
          <p>
            {successMessage}
          </p>
        </div>
      {/if}
    </div>
  </div>
</div>

<style>
  .contact-banner {
    background: var(--deep-blue);
    box-shadow: 0 6px 12px rgba(0 0 0 / 45%);
    margin-bottom: 60px;
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
    grid-gap: 1rem;
    margin-bottom: 1rem;
  }
  .btm-row {
    display: grid;
    grid-template-columns: 2fr 1fr;
    grid-gap: 1rem;
  }

  .right p {
    color: white;
  }

  .center {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  @media (max-width: 1024px) {
    .contact-banner {
      padding-bottom: 3rem;
    }
    .contact-banner .container {
      grid-template-columns: 1fr;
    }
    .left h3 br {
      display: none;
    }

    form {
      max-width: 780px;
      margin: auto;
    }
  }

  @media (max-width: 700px) {
    .top-row, .btm-row {
      grid-template-columns: 1fr;
    }
  }

</style>