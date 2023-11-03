<script>
  import Form from './Form.svelte';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<div>
		<span class="translatePageBtn">ترجم</span>
		<span class="translatePageBtn">translate</span>
	</div>
	<h1>Collections to learn and memorise</h1>
	<h2><a href="/collections">Browse availavle collections</a></h2>
  
	<Form />
</section>

<style>
	.translatePageBtn{
	       border: .5px solid gray;
	       padding: 5px;
	       border-radius: 5px;
	   }
</style>