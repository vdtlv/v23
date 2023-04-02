<script>
	import me from '$lib/images/vdtlvpic.webp';
	import me_fallback from '$lib/images/vdtlvpic.png';
	import fm from '$lib/images/fmlogo.webp';
	import fm_fallback from '$lib/images/fmlogo.png';
    let y = 0;
</script>
<svelte:window bind:scrollY={y}/>

<section class="intro">
<div style="scale: {1 - Math.min(y / 200)}; opacity: {1 - ( y / 200)};">
	<h5>
		Hi! I'm
		<span class="me">
			<picture>
				<source srcset={me} type="image/webp" />
				<img src={me_fallback} alt="" />
			</picture>
		</span>
		Slava (he/him), working as a&nbsp;product designer at 
		<span class="fm">
			<picture>
				<source srcset={fm} type="image/webp" />
				<img src={fm_fallback} alt="" />
			</picture>
		Fitmost. Also trying to develop pet-projects in my spare time.
	</h5>
</div>
</section>

<style>
section {
    z-index: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;


}

/* –––––– intro settings –––––– */
h5{
    max-width: 540px;
    line-height: 44px;
    margin: 140px 0 98px  0;
    text-align: center;
}
img {
    width: 40px;
    height: 40px;
    margin-bottom: -8px;
    transition: transform 0.3s ease-in;
}
.me img {
    border-radius: 12px;
}
img:hover {
    transform: scale(1.3) rotate(0.04turn);
    transition: transform 0.5s ease-out;
}
.me img:hover {
    transform: scale(1.3) rotate(-0.02turn);
    transition: transform 0.5s ease-out;
}

</style>