<script>

  import { Route } from 'svelte-routing';
  import Index from '../routes/Index.svelte';
  import Login from '../routes/Login.svelte';
  import Register from '../routes/Register.svelte';

</script>

<main>
  <Route path="/index"><Index/></Route>
  <Route path="/login"><Login/></Route>
  <Route path="/register"><Register/></Route>
  <Route path="/"><Index /></Route>
</main>

<style>
</style>
