<script>
	import { onMount } from 'svelte';
  
	import { formatDistanceToNow } from 'date-fns';
  
	const email = 'a.kuzmich@innopolis.university';
	const apiUrl = `https://fwd.innopolis.university/api/hw2?email=${email}`;
  
	let comicData = {
	  month: '',
	  num: 0,
	  link: '',
	  year: '',
	  news: '',
	  safe_title: '',
	  transcript: '',
	  alt: '',
	  img: '',
	  title: '',
	  day: '',
	};
  
	let publicationDate = new Date();
	let isComicDisplayed = false; // Flag to track if the comic is displayed or not
  
	onMount(() => {
	  // Don't fetch comic data on mount. Wait for the button click.
	});
  
	function refreshComic() {
	  fetch(apiUrl)
		.then((response) => response.text())
		.then((text) => {
		  const trimmedText = text.trim();
		  const number = parseFloat(trimmedText);
		  const comicUrl = `https://fwd.innopolis.university/api/comic?id=${number}`;
  
		  return fetch(comicUrl);
		})
		.then((response) => response.json())
		.then((comicDataResponse) => {
		  comicData = comicDataResponse;
		  publicationDate = new Date(
			parseInt(comicDataResponse.year),
			parseInt(comicDataResponse.month) - 1,
			parseInt(comicDataResponse.day)
		  );
		  isComicDisplayed = true; // Set the flag to true after successfully fetching the comic
		});
	}
  </script>
  
  
  
  <section class="api-experience">
	<p>
	  Here I want to show my work with API. Click the button below to see the comic generated especially for you.
	</p>
  </section>
  
  <section class="comic-info">
	<button on:click={refreshComic} class="box-button">₊‧⁺˖⋆ Show me! ⋆˖⁺‧₊</button>
	<!-- <p>{displayText}</p> -->
  </section>
  <main>
	{#if isComicDisplayed} <!-- Display the comic info only if isComicDisplayed is true -->
	  <h1 id="comic-title">{comicData.safe_title}</h1>
	  <p id="comic-date">Publication Date: {publicationDate.toLocaleDateString()}</p>
	  <p id="comic-date-released">Released {formatDistanceToNow(publicationDate, { addSuffix: true })}</p>
	  <img id="comic-image" src={comicData.img} alt={comicData.alt} />
	 
	{/if}
  </main>
  
  
  <style>
	main {
    text-align: center;
	margin-bottom: 20px;
  }
    main h1 {
		font-size: 20px;
		margin-top: 1px;
		font-weight: bold;
  }
  .api-experience {
    color: #4e3824;
    background-color: rgb(244, 191, 127);
    padding: 10px;
    margin: 20px auto 0;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    width: 780px;
  }
	
  
	.comic-info {
	  color: #4e3824;
	  padding: 10px;
	  margin-bottom: 20px;
	  display: flex;
	  flex-direction: column;
	  justify-content: center;
	  align-items: center;
	  text-align: center;
	}
  
	.box-button {
	  margin-top: 20px;
	  background-image: url('https://img.freepik.com/free-vector/hand-painted-watercolor-abstract-watercolor-background_23-2149001482.jpg?w=1060&t=st=1687279153~exp=1687279753~hmac=b9d067dabffdb21ce1e987de2fb3c127a002abe8d5f2f9e785a676785a9bc2d8');
	  opacity: 0.8;
	  background-size: cover;
	  background-position: center;
	  color: rgb(19, 10, 2);
	  border: none;
	  padding: 20px 200px;
	  border-radius: 10px;
	  text-align: center;
	  cursor: pointer;
	  font-weight: bold;
	}
  </style>
  