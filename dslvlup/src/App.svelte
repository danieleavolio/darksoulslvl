<script lang="ts">
    import {stats} from "./stores/statsStore";
	import Button from "./components/Button.svelte";

	// Logic for stat
	let choice:string = '____';
	let amount:string = '____';
    let behavior = ():void =>{
		//Pick a stas from the store randomly
        choice = $stats[(Math.floor(Math.random() * $stats.length))];

		//Pick the amount
		let random:number = Math.floor(Math.random() * 3);
		switch(random){
			case 0:
				amount = "Use all";
				break;
			case 1:
				amount = "1 Level";
				break;
			case 2:
				amount = "1 level or Pick again";
				break;
		}
    }

</script>

<main>
	
	<div class="heading-div">
		<h1 class="heading">Dark Souls Random Stats <span>Lvl UP</span></h1>
		<p class="quote">" Level up a stat based on fate. Don't cheat the amount! "</p>
	</div>
	<div class="components-div">
		<div class="choice">
			<p>Stat:</p>
			<p class="fate">{choice}</p>
		</div>
		<div class="choice">
			<p>Amount:</p>
			<p class="fate">{amount}</p>
		</div>
		<Button on:click={behavior} content={"Pick your fate 💀"}/>
	</div>

	<footer>Coded by <span> Daniele Avolio</span></footer>
</main>

<style>

	main{
		height: 100%;
		background-color: #252C33;
		color: #EEEEEE;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
	}

	span{
		color:#f6c90e
	}
	.components-div{
		background-color: #3A4750;
		margin: 1.6rem;
		border-radius: 10px;
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
		align-items: center;
		height:fit-content;
	}


	.heading-div{
		margin:1rem;
	}
	.heading{
		font-size: 3rem;
		text-align: center;
		margin:0;;
		font-weight: 700;
	}


	.choice{
		font-size: 2.5rem;
		font-weight: 600;
		text-align: center;
	}
	
	.quote{
		font-size: 1.3rem;
		font-style: italic;
		text-align: center;
		color: #f6c90e;
		text-decoration: underline;
	}

	.fate{
		color: #f6c90e;
	}

	footer{
		font-style: italic;
		text-align: center;
		font-weight: 300;
		margin-bottom:1rem;
	}


	/* Media queries */

	@media screen and (min-width:700px){
		.components-div{
			flex-direction: row;
		}
	}
</style>