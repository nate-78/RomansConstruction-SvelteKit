<script>
  export let label = '';
  export let fieldName = '';
  export let fieldType = 'text';
  export let change = (e) => {};

  let isActive = false;
  let value = '';

  const onFocus = () => {
    isActive = true;
  };

  const onChange = (e) => {
    value = e.target.value;
    change(e);
    if (value != '') {
      isActive = true;
    } else {
      isActive = false;
    }
  };

  const onBlur = () => {
    if (value != '') {
      isActive = true;
    } else {
      isActive = false;
    }
  }
</script>

<div class="form-control {isActive ? 'active' : ''}">
  <label for="{fieldName}">{label}</label>
  <input type={fieldType} name={fieldName} id={fieldName} value={value}
    on:focus={onFocus}
    on:change={onChange}
    on:blur={onBlur}  
  />
</div>

<style>
  .form-control {
    width: 100%;
    position: relative;
  }
  .form-control label {
    position: absolute;
    left: 5px;
    top: 15px;
    transition: .3s;
    color: #777;
  }
  .form-control.active label {
    top: 0;
    font-size: .9rem;
  }
  .form-control input {
    height: 34px;
    width: 100%;
    background: white;
    border: none;
    padding: 13px 5px 0;
    border-bottom: 3px solid var(--mustard);
  }
</style>