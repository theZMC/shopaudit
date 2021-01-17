<script>
import Header from "./Header.svelte";
import InventoryList from "./InventoryList.svelte";
import Footer from "./Footer.svelte";
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.gstatic.com">
	<link href="https://fonts.googleapis.com/css2?family=Fira+Sans+Extra+Condensed:ital,wght@0,400;0,700;1,900&display=swap" rel="stylesheet">
</svelte:head>
<div>
	<Header />
	<InventoryList />
	<Footer />
	<!-- <InventoryItem 
		productName="Michelin XTA2 255/70R22.5"
		productNumber="M72331"
	/> -->
</div>
<style>
	:global(html, body, div, span, applet, object, iframe,
			h1, h2, h3, h4, h5, h6, p, blockquote, pre,
			a, abbr, acronym, address, big, cite, code,
			del, dfn, em, img, ins, kbd, q, s, samp,
			small, strike, strong, sub, sup, tt, var,
			b, u, i, center,
			dl, dt, dd, ol, ul, li,
			fieldset, form, label, legend,
			table, caption, tbody, tfoot, thead, tr, th, td,
			article, aside, canvas, details, embed, 
			figure, figcaption, footer, header, hgroup, 
			menu, nav, output, ruby, section, summary,
			time, mark, audio, video) {
		margin: 0;
		padding: 0;
		border: 0;
		font-size: 100%;
		font: inherit;
		vertical-align: baseline;
	}
	/* HTML5 display-role reset for older browsers */
	:global(article, aside, details, figcaption, figure, 
			footer, header, hgroup, menu, nav, section) {
		display: block;
	}
	:global(body) {
		line-height: 1;
	}
	:global(ol, ul) {
		list-style: none;
	}
	:global(blockquote, q) {
		quotes: none;
	}
	:global(blockquote:before, blockquote:after,
			q:before, q:after) {
		content: '';
		content: none;
	}
	:global(table) {
		border-collapse: collapse;
		border-spacing: 0;
	}
	:global(html){
		font-size: 8px;
	}
	:global(h1,h2,h3,h4,h5,h6){
		font-family: "Fira Sans Extra Condensed", Verdana, Geneva, Tahoma, sans-serif;
		font-weight: bolder;
	}
	:global(body){
		font-family: "Fira Sans Extra Condensed", Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
	}
	@media only screen and (min-width: 300px){
		:global(html){
			font-size: 10px;
		}
	}
	@media only screen and (min-width: 380px){
		:global(html){
			font-size: 12px;
		}
	}
	@media only screen and (min-width: 580px){
		:global(html){
			font-size: 14px;
		}
	}
	:global(body, html){
		height: 100vh;
		display: flex;
		flex-direction: column;
	}
	@media only screen and (max-width: 600px){
		div{
			display: grid;
			grid-template-rows: auto 1fr auto;
			height: 100vh;
		}
	}
</style>