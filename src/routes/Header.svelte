
<script>
	import { page } from '$app/stores';

	import { base } from '$app/paths';
	let title = "Heyy, I am Alex!";
  </script>
  
  <header>
    <section class="header">
      <h1>{title}</h1>
    </section>
  </header>


<header>
	
	<nav>
	
		<ul>
			<li aria-current={($page.url.pathname === '/' || $page.url.pathname.startsWith('/home')) ? 'page' : undefined}>
				<a href="{base}/">Home</a>
			</li>
		</ul>
		<ul>
			<li aria-current={$page.url.pathname === '/bio' ? 'page' : undefined}>
				<a href="{base}/bio">Bio</a>
			</li>
		</ul>
		<ul>
			<li aria-current={$page.url.pathname === '/portfolio' ? 'page' : undefined}>
				<a href="{base}/portfolio">Portfolio</a>
			</li>

		
			<li aria-current={$page.url.pathname === '/comic' ? 'page' : undefined}>
				<a href="{base}/comic"> API experience</a>
			</li>
			<li aria-current={$page.url.pathname === '/socialIcons' ? 'page' : undefined}>
				<a href="{base}/socialIcons"> Media Links</a>
			</li>
		</ul>
	
	</nav>

	</header>

<style>

    .header {
	color: #4e3824;
    background-color: rgb(244, 191, 127);
    padding: 10px;
	margin-top:20px;
    text-align: center;
    border-radius: 10px;
    margin-bottom: 20px;
	margin-left: -20px;
	margin-right: -20px;
    }

	nav {
		display: flex;
		justify-content: center;
		color: #4e3824;
      --background: rgba(244, 191, 127, 0.7); 
		/* --background: rgba(255, 255, 255, 0.7); */
	}

	
	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid rgb(194, 74, 23);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		color: var(--color-text);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: rgb(194, 74, 23);
		/* color: var(--color-theme-1); */
	}

</style>
