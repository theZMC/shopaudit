<script>
import InventoryItem from "./InventoryItem.svelte";

</script>

<main>
	<InventoryItem 
		productName="Michelin XTA2 255/70R22.5"
		productNumber="M72331"
	/>
</main>

<style>
	:global(html){
		font-size: 6px;
	}
	@media only screen and (min-width: 300px){
		:global(html){
			font-size: 8px;
		}
	}
	@media only screen and (min-width: 380px){
		:global(html){
			font-size: 10px;
		}
	}
	@media only screen and (min-width: 580px){
		:global(html){
			font-size: 12px;
		}
	}
</style>