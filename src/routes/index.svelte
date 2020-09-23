<script context="module">
	export function preload({ params, query }) {
		return this.fetch(`blog.json`).then(r => r.json()).then(posts => {
			return { posts };
		});
	}
</script>

<script>
	import  Post from '../components/Post.svelte';
	export let posts;
</script>

<style>
	.Posts {
		display: grid;
		justify-content: space-between;
		grid-gap: 15px;
		grid-template-columns: 1fr;
	}
</style>

<svelte:head>
	<title>Edy Joel</title>
	<meta name="description" content="En este blog encontras términos relacionados a Microeconomía." />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:site" content="@edyjoelx" />
	<meta name="twitter:creator" content="@edyjoelx" />
	<meta name="twitter:title" content="Blog Microeconómico" />
	<meta name="twitter:description" content="En este blog encontras términos relacionados a Microeconomía." />
	<meta name="twitter:image" content="https://arepa.s3.amazonaws.com/blogpost-cover.png">

	
	<meta name="og:title" content="Blog Microeconómico">
	<meta name="og:description" content="En este blog encontras términos relacionados a Microeconomía.">
	<meta name="og:image" content="https://arepa.s3.amazonaws.com/blogpost-cover.png">
	<meta name="og:url" content="https://diccionarioedy.netlify.app" />
	<meta name="og:site_name" content="Blog Microeconómico">
	<meta name="og:locale" content="es_ES" />
	<meta name="og:type" content="article">
	<meta name="fb:app_id" content="">
	
</svelte:head>

<div class="Home">
	<div class="Posts">
		{#each posts as post}
			 <!-- content here -->
			 <Post {post} />
		{/each}
	</div>
</div>
