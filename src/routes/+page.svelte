<script lang="ts">

	import Header from './Header.svelte';
	import Intro from './Intro.svelte';

	import { inview } from 'svelte-inview';

	let isInView:Boolean;
	let scrollDirection: ScrollDirection;
	const options = {
		rootMargin: '-50px',
    	unobserveOnEnter: true,
	};
	let y = 0;
</script>

<svelte:window bind:scrollY={y}/>

<svelte:head>
	<title>vdtlv</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<Header />

<div class="container" >
	<section class="projects" id="myprojects">

		<Intro  />
		<div class="project rot">
			rightontrek
		</div>
		<div class="pr educt" 
		use:inview={options}
		on:inview_change={(event) => {
		  const { inView, entry, scrollDirection, observer, node} = event.detail;
		  isInView = inView;
		}}
		on:inview_enter={(event) => {
		  const { inView, entry, scrollDirection, observer, node} = event.detail;
		  isInView = inView;
		}}
		on:inview_leave={(event) => {
		  const { inView, entry, scrollDirection, observer, node} = event.detail;
		  isInView = inView;
		}}
		on:inview_init={(event) => {
		  const { observer, node } = event.detail;
		}}>
		{isInView ? 'Hey I am in the viewport' : 'Bye, Bye'} 
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

<section class="contacts" id="contacts" style="background-color: red; color: white; height 500px; width:500px"> heey</section>

<style>

	/* –––––– prjects settings –––––– */

	.container {
		height: 100vh;
	}

	section::-webkit-scrollbar{
    	display: none;
  	}

	.projects {
		position: sticky;
		top: 54px;
		/*display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;

		overflow-y: scroll;
				
		background-color: var(--color-bg-2);
		*/

		

		height: calc(100vh - 54px);
		
		overflow-y: scroll;
		scroll-snap-type: y mandatory;	
		-webkit-overflow-scrolling: touch;
	}

	
	.project {
		height: calc(100vh - 54px);
		text-align: center;
		
		scroll-snap-align: start;
		scroll-snap-stop: always;

		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.pr {
		height: calc(200vh - 54px);
		text-align: center;
		
		scroll-snap-align: start;
		scroll-snap-stop: normal;

		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	/* –––––– rot settings –––––– */
	.rot {
		background-color: orange;
	}

	/* –––––– educt settings –––––– */

	.educt {
		background-color: rgb(3, 121, 217);
	}
</style>
