<script>
	let socialLinks = [
	  {
		name: "Instagram",
		link: "https://www.instagram.com/fegur_natturunnar/?hl=ru",
		icon: "portrait"
	  },
	  {
		name: "GitHub",
		link: "https://github.com/pferdlexxie",
		icon: "code"
	  },
	  {
		name: "Telegram",
		link: "https://t.me/pferdlexxie",
		icon: "send"
	  },
	  {
		name: "Email",
		link: "mailto:alexandrakuzmich@mail.ru",
		icon: "mail"
	  }
	];
  </script>
  
  <section class="social-container">
	<h2>Contact Me!</h2>
	<div class="social-icons">
	  {#each socialLinks as socialLink}
		<div class="social-link">
		  <a href={socialLink.link} target="_blank" rel="noopener noreferrer">
			<span class="material-icons">{socialLink.icon}</span>
		  </a>
		  <p>{socialLink.name}</p>
		</div>
	  {/each}
	</div>
  </section>
  
  <style>
	.social-container {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	  text-align: center;
	  margin-top: 10px;
	  color:#4e3824
	}

	.social-container h2 {
    font-size: 25px; /* Increase the font-size value */
	margin-top: 10px;
    margin-bottom: 30px;
  }
  
	.social-icons {
	  display: flex;
	  justify-content: center;
	  margin-top: 20px;
	}
  
	.social-link {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	  margin: 0 10px;
	}
  
	.social-link p {
	  margin-top: 10px;
	}
  
	.social-icons a {
	  display: inline-block;
	  margin: 0 30px; 
	  font-size: 15px;
	  color: #ac7c59;
	  text-decoration: none;
	}
  
	.social-icons a:hover {
	  color: #c28233c3;
	}

	.social-icons a span {
    display: inline-block;
    transform: scale(2); 
  }
  </style>
  
  <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
  