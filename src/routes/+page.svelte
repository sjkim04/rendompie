<script lang='ts'>
    const sleep = (ms: number) => new Promise(
	    resolve => setTimeout(resolve, ms)
    );
    const morse = async (str: string) => {
        switch (str) {
            case 'long':
                await changeBk(750);
                await sleep(250);
                break;
            case 'short':
                await changeBk(250);
                await sleep(250);
                break;
        }
    }
    const getRandomInt = (min: number, max: number) => {
	    min = Math.ceil(min);
	    max = Math.floor(max);
	    return Math.floor(Math.random() * (max - min + 1) + min);
    };

    let i = '#000000';
    const changeBk = async (ms: number) => {
        i = '#ffffff';
        await sleep(ms);
        i = '#000000'
    }

    setInterval(async () => {
        await morse('long');
        await morse('short');
        await morse('short');
        await morse('long');
        await morse('short');
        await sleep(750);

        await morse('short');
        await morse('short');
        await morse('short');
        await morse('short');
        await sleep(750);

        await morse('short');
        await sleep(750);

        await morse('short');
        await morse('long');
        await morse('long');
        await morse('short');
        await sleep(750);
    }, 3000);
</script>

<div class="container" style="--bkcolor: {i};">
No Hints Here! (EX of EX) 
</div>


<style>
.container {
	height: 100vh;
	width: 100vw;

    color: var(--bkcolor);

	background-color: var(--bkcolor);
}
</style>
