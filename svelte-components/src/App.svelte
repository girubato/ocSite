<script>
  import CharacterThoughts from "./components/characterThoughts.svelte";
import OcList from "./components/ocList.svelte";

	
	
	

	let leftCharacter;
	let rightCharacter;

	
	let duplicate;

$: if(leftCharacter === rightCharacter) 
		duplicate = 1;
	else
		duplicate = 0;
</script>

<main>
	<div class="container">
		<div class="Left-Character-Selector">
			<OcList bind:selected={leftCharacter} />
		</div>

		<div class="Character-Portrait-Container">
		<div class="Left-Character-Portrait">
			
			{leftCharacter}
			<div class="Left-Character-Thoughts">
				<CharacterThoughts selectedCharacter={leftCharacter} leftOrRight="left"/>
			</div>
		</div>

		<div class="Right-Character-Portrait">
			{rightCharacter}
			{#if duplicate}
				Is a duplicate
			{/if}
				<div class="Right-Character-Thoughts">
					<CharacterThoughts selectedCharacter={rightCharacter} leftOrRight="right"/>
				</div>
		</div>
	</div>
		<div class="Right-Character-Selector">
			<OcList bind:selected={rightCharacter} />
		</div>
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	.container{
		display:grid;
		grid-template-columns: repeat(5, 20%);
	}

	.Left-Character-Selector{
		grid-column: 1;
		background-color: rgba(00, 200, 00, 0.3);
	}

	.Left-Character-Portrait{
		grid-column:  2;
		background-color: rgba(100, 100, 100, 0.3);
	}
	
	.Left-Character-Thoughts{
		background-color: rgba(100, 100, 100, 0.3);
	}

	.Character-Portrait-Container{
		grid-column: 2/5;
		display:grid;
		grid-template-columns: repeat(5, 20% [col-start]);
	}


	.Right-Character-Selector{
		grid-column: 5;
		background-color: rgba(00, 0, 200, 0.3);
	}

	.Right-Character-Portrait{
		grid-column: 4;
		background-color: rgba(100, 100, 100, 0.3);
	}
	.Right-Character-Thoughts{
		background-color: rgba(100, 100, 100, 0.3);
	}
</style>