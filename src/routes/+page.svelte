<script>
	import Header from './Header.svelte';
	import Intro from './Intro.svelte';
	let ovrflw = 'auto';

</script>

<svelte:head>
	<title>vdtlv</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<Header />
<Intro />
<div style="height: 400vh;">
<section class="projects" id="myprojects">
	<div class="project rot">
		rightontrek
	</div>
	<div class="project educt"> 
		educt ы
	</div>
	<div class="project rot">
		rightontrek
	</div>
	<div class="project educt">
		educt
	</div>
</section>
</div>


<style>

	/* –––––– prjects settings –––––– */

	section::-webkit-scrollbar{
    	display: none;
  	}

	.projects {
		/*display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;

		overflow-y: scroll;
				
		*/

		padding: 2rem;

		background-color: var(--color-bg-2);
		border-radius: 6rem;

		width: calc(100%-2rem);
		height: calc(100vh - 114px);
		overflow-y: auto;

		position: sticky;
		top: 54px
	}

		.projects > *:not(:last-child) {
    	margin-bottom: 2rem; 
	} 

	/* –––––– rot settings –––––– */
	.project {
		width: 100%;
		height: 512px;
		border-radius: 4rem;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.rot {
		background-color: orange;
	}

	/* –––––– educt settings –––––– */

	.educt {
		background-color: rgb(3, 121, 217);
	}
</style>
