<script>
	import welcome from '$lib/images/forest.jpg';
	// import welcome_fallback from '$lib/images/svelte-welcome.png';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<h1>
		<span class="welcome"></span>
		<p> Welcome to my personal website</p>
	</h1>
	<img src={welcome} alt="SvelteKit" class="photo" />


</section>

<style>
	.photo {
		width: 780px;
		height: 270px;
	}
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		/* flex: 0.6; */
	}

	h1 {
		width: 100%;
    font-size: 23px; /* Adjust the font size as needed */
    text-align: center;
	margin-top: -10px; 
	margin-bottom: 5px;


	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		
	}

</style>
