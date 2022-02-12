<script>
  import {
    Collapse,
    Navbar,
    NavbarToggler,
    NavbarBrand, 
    Button,
    Image
  } from 'sveltestrap';
  let isOpen = false;
  export let isLogged = false;
  function handleUpdate(event) {
    isOpen = event.detail.isOpen;
  }
  import { Link } from 'svelte-routing';
  
</script>

  <Link to="/">
    <NavbarBrand>
      <Image src="../static/img/Logo_OpenClassrooms.png" alt="logo" width="40" height="40" class="d-inline-block align-text-center me-2" />
      Openclassrooms
    </NavbarBrand>
  </Link>
  <NavbarToggler on:click={() => (isOpen = !isOpen)} />
  <Collapse {isOpen} navbar expand="lg" class="" on:update={handleUpdate}>
    <div class="d-flex flex-lg-row flex-column justify-content-end flex-fill gap-3">
      {#if isLogged}
        <div class="d-grid gap-2 d-flex justify-content-lg-end justify-content-center">
          <Link to="dashboard">
            <Button color="dark">Tableau de bord</Button>
          </Link>
          <Button outline color="dark">Se déconnecter</Button>
        </div>
      {:else} 
        <div class="d-grid gap-2 d-flex justify-content-lg-end justify-content-center">
          <Link to="login">
            <Button color="dark">Se connecter</Button>
          </Link>
          <Link to="register">
            <Button outline color="dark">S'enregistrer</Button>
          </Link>
        </div>
      {/if}  
    </div>
  </Collapse>

<style>
</style>