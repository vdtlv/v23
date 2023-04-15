<script lang="ts">
	import { page } from '$app/stores';

	let current = 'intro';

	function scrollIntoView({ target }: {target:any}) {
		const el = document.querySelector(target.getAttribute('href'));
		if (!el) return;
    el.scrollIntoView({
      behavior: 'smooth'
    });
  }

	let y = 0;
</script>
<svelte:window bind:scrollY={y}/>

<header>
	<div class="left-corner">
			<p><!--VDTLV--> {y} </p>
	</div>

	<nav>
		<a href="#myprojects" 
		class:active="{current === 'myprojects'}"
		on:click="{() => current = 'myprojects'}"
		on:click|preventDefault={scrollIntoView}>Projects</a>
		<a href="#about"
		class:active="{current === 'about'}"
		on:click="{() => current = 'about'}"
		on:click|preventDefault={scrollIntoView}>About</a>
		<a href="#contacts"
		class:active="{current === 'contacts'}"
		on:click="{() => current = 'contacts'}"
		on:click|preventDefault={scrollIntoView}>Contacts</a>
	</nav>

	<div class="right-corner">
		<a href="https://github.com/sveltejs/kit">
			<!--<img src={github} alt="GitHub" />-->
			EN
		</a>
	</div>
</header>

<style>
	header {
		z-index: 100;
		position: fixed;
		top: 0;
  		right: 0;
		height: 22px;
		width: calc(100% - 4rem);
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 1rem 2rem;
	}

	.left-corner, .right-corner {
		width: 64px;
		font-weight: 700;
		font-size: 1rem;
	}

	.left-corner p {
		margin: 0;
	}

	.right-corner {
		text-align: right;
	}

	nav {
		display: flex;
		height: 100%;
		align-items: center;
	}

	nav > a {
		opacity: .6;
	}
	a {
		font-weight: 700;
		border-radius: 6px;
		color: var(--color-text);
		text-decoration: none;
		padding: 4px 8px;
		transition: 0.2s;
  	}
 	a:hover {

		background-color: var(--hover);
		cursor: pointer;
  	}

	.active {
		opacity: 1;
	}
  	a:visited {
    	text-decoration: none;
  	}
</style>
