<script>
    import { createEventDispatcher } from 'svelte'
    
    import ProgressBar from './ProgressBar.svelte';

    const totalSeconds = 20;

    let secondLeft = totalSeconds;
    
    let isRunning = false;

    let dispatch = createEventDispatcher();

    function startTimer() {
        isRunning = true;
        const timer = setInterval(() => {
            secondLeft -= 1;

            if (secondLeft == 0) {
                clearInterval(timer)
                isRunning = false;
                secondLeft = totalSeconds;
                dispatch('end');
            }
        }, 1000)
    
    }

    let progress = 0;
    $:progress = (100 - secondLeft * 5);

</script>

<style>
    h2 {
        margin: 0;
    }

    .start {
        background-color: rgb(154, 73, 73);
        width: 100%;
        margin: 10px 0;
    }

    .start[disabled] {
        background-color: gray;
        cursor: not-allowed;
    }
</style>

<div bp="grid">
    <h2 bp="offset-5@md 4@md 12@sm">
        Seconds Left: {secondLeft}
    </h2>
</div>

<ProgressBar {progress}/>

<div bp="grid">
    <button disabled={isRunning} bp="offset-5@md 4@md 12@sm" class="start" on:click={startTimer}>Start</button>
</div>