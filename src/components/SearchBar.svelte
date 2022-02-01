<script>
  import {
    Form,
    Input
  } from 'sveltestrap';

  export let searchText;
</script>

<Form class="my-2 my-lg-0">
  <Input class="form-control" type="text" placeholder="Rechercher" autocomplete="off" aria-label="Search" bind:value={searchText} on:input />
</Form>

<style>

</style>