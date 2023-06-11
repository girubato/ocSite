<script>
  import BlueComponent from "./components/blueComponent.svelte";
import RedComponent from "./components/redComponent.svelte";

	export let name;

	

	let leftCharacter ;
	let rightCharacter;

</script>

<main>
	<div class="container">
		<div class="Left-Character-Selector">
			Left Selected
		</div>

		<div class="Character-Portrait-Container">
		<div class="Left-Character-Portrait">
			Left Character Portrait
			<div class="Left-Character-Thoughts">
				Left Character Thoughts
			</div>
		</div>

		<div class="Right-Character-Portrait">
			Right Character Portrait
				<div class="Right-Character-Thoughts">
					Right Character Thoughts
				</div>
		</div>
	</div>
		<div class="Right-Character-Selector">
			Right Selected
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
		grid-template-columns: repeat(4, 25%);
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
		grid-column: 2/4;
		display:grid;
		grid-template-columns: repeat(5, 20% [col-start]);
	}


	.Right-Character-Selector{
		grid-column: 4;
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