<script>
	import Router from 'svelte-spa-router';
	import Signin from './routes/Signin.svelte';
	import Contracts from './routes/ Contracts.svelte'
    import Home from "./routes/Home.svelte";
	import Registry from './routes/Registry.svelte';
</script>

<Router routes={{
    '/': Home,
	'/signin/': Signin,
	'/registry/': Registry,
	'/cotractpage/': Contracts
}} />

<style>
	


</style>