<script>
	import Register from './routes/Register.svelte';
	import Footer from './components/Footer.svelte';
	import Navigation from './components/Navigation.svelte';
	import Index from "./routes/index.svelte";
	import { Router, Link, Route } from "svelte-routing";
import Login from "./routes/Login.svelte";
	export let url="";
</script>
<svelte:head>
	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
	<script src="https://kit.fontawesome.com/772f489e77.js" crossorigin="anonymous"></script>
	<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
</svelte:head>

<Router url="{url}">
<nav>
	<Navigation/>
</nav>
<div>
	<Route path="/index" component={Index}></Route>
  <Route path="/login" component={Login}></Route>
  <Route path="/register" component={Register}></Route>
  <Route path="/"><Index /></Route>
  </div>

</Router>

<Footer />

<style>

</style>