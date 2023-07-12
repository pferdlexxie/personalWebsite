<svelte:head>
	<title>Bio</title>
</svelte:head> 

<script>
	
	import bioIMG from '$lib/images/profile_cop_(3).jpg';
	let height = 300;
	let bioLine1 = `₊‧⁺˖⋆ 18 years old front-end learner ⋆˖⁺‧₊`
	let bioLine2 = `₊‧⁺˖⋆ in love with folk and folk-rock music ⋆˖⁺‧₊`
    let bioLine3 = `₊‧⁺˖⋆ Moscow ⤏ Innopolis ⋆˖⁺‧₊`
  </script>
  
  <div class="container">
	<img src={bioIMG} alt="SvelteKit" height={height} class="profile-photo" />
  
	
	<section class="bio">
	  <h2>About Me</h2>
	  <p>{bioLine1}</p>
	  <p>{bioLine2}</p>
	  <p>{bioLine3}</p>
	</section>
  </div>
  
	<style>
	   .bio {
		background-color: rgb(244, 191, 127);
		padding-left: 40px;
		padding-right: 40px;
		padding-bottom: 30px;
		padding-top: 30px;
		margin-top: 30px;
		border-radius: 20px 10px 0;
	  }
  
  
	  .bio h2 {
		font-size: 24px;
		margin-top: 1px;
		margin-bottom: 30px;
		text-align: center;
	  }
  
  
	  .bio p {
		font-size: 16px;
		text-align: center;
		line-height: 20px;
		margin-bottom: 10px;
	  }
  
	  .profile-photo {
		border-radius: 30%;
	  }
  
  
	  .container {
		display: flex;
		align-items: flex-start;
		margin-top: 30px;
	  }
  
  
	  .container .profile-photo {
		margin-right: 30px;
	  }
  
  
	  .container .bio {
		flex: 1;
		font-weight: bold;
	  }
  
	</style>
	