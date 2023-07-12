<svelte:head>
	<title>Portfolio</title>
</svelte:head> 

<script>
    let projects = [
      {
        imageSrc: "https://aminus3.s3.amazonaws.com/image/g0042/u00041500/i02283774/2dbda63a08ce7b1bbcc26ebc8ecf3c51_giant.jpg",
        altText: "portfolio photo",
        height: 200,
        overlayText: "Website for a music group",
      },
      {
        imageSrc: "https://aminus3.s3.amazonaws.com/image/g0032/u00031911/i01909139/2a8987593e8066a63662cd84b4799eaa_giant.jpg",
        altText: "portfolio photo",
        height: 200,
        overlayText: "Website for a pottery",
      },
      {
        imageSrc: "https://marchelache.com/storage/f6/71/f67198bb-32c5-47f2-a78d-dcdb6e33447e/c/zdomyqzl2z-xl.jpg",
        altText: "portfolio photo",
        height: 200,
        overlayText: "Website for a dog shelter",
      },
    ];
    
  </script>

<div class="header">
	<span>Projects I would like to do. Analogue to portfolio</span>
</div>
  <section class="portfolio">
    <!-- <p>
      Projects I would like to do. Analogue to portfolio
    </p> -->

    {#each projects as project}
      <div class="image-container">
        <img src={project.imageSrc} alt={project.altText} height={project.height} class="portfolio-photo" />
        <div class="text-overlay">
          <p>{project.overlayText}</p>
        </div>
      </div>
    {/each}
  </section>
  
  <style>
	.header {
    padding-top: 0px;
    padding-bottom: 15px;
    font-size: 20px;
  text-align: center;

}

.header span {
	padding: 15px;
  display: inline-block;
  background-color: rgb(244, 191, 127);
  color: #4e3824;
  border-radius: 7px;
}

    
    .portfolio {
      color: #4e3824;
      background-color: rgb(244, 191, 127);
      /* padding: 10px; */
      /* margin-bottom: 20px; */
      /* margin-top: 10px;  */
      display: flex;
      justify-content: center;
      align-items: center; 
      text-align: center; 
      font-weight: bold;
    }
  .portfolio-photo {
    width: 240px;
    height: 240px;
	margin-top: 20px;
    object-fit: cover;
	margin-bottom: 20px;
	margin-left: 7px;
	margin-right: 7px;
	
  }


  .portfolio-photo:hover {
    filter: grayscale(100%);
  }
  .image-container:hover img {
  filter: grayscale(100%);
}


 
  .image-container {
  position: relative;
  display: inline-block;


}


.text-overlay {
  position: absolute;
  top: 50%;
  left: 47%;
  transform: translate(-45%, -50%);
  background-color: #ac7c59;
  color: #2c1f13;
  font-weight: bold;
  padding: 10px;
  width: 190px;
  text-align: center;
  visibility: hidden;
  opacity: 0;
  transition: visibility 0s, opacity 0.5s;
}


.image-container:hover .text-overlay {
  visibility: visible;
  opacity: 1;
}


  </style>
  