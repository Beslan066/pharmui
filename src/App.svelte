<script>
	import Router from 'svelte-spa-router';
	import Signin from './routes/Signin.svelte';
	import Contracts from './routes/ Contracts.svelte'
    import Home from "./routes/Home.svelte";
</script>

<Router routes={{
    '/': Home,
	'/signin/': Signin,
	
	'/cotractpage/': Contracts
}} />

<style>
	


</style>