<script>
	import HowTo from './HowTo.svelte';
	import Timer from './Timer.svelte';

	let audio;

	function timerEnds(e) {
		audio.play();
	}
</script>

<style>
	h1, h3 {
		text-align: center;
	}
</style>
<h1>Handwashing App</h1>

<Timer on:end={timerEnds} />
<HowTo/>

<h3>
	<a href="https://www.who.int/gpsc/5may/Hand_Hygiene_Why_How_and_When_Brochure.pdf">Picture Source</a>
</h3>
<h3>
	<a href="https://www.wavsource.com/snds_2020-10-01_3728627494378403/sfx/alarm_beep.wav">Sound Source</a>
</h3>

<audio bind:this={audio}>
	<source src="sound.wav" />
</audio>