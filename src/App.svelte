<script>
import Header from "./Header.svelte";
import InventoryList from "./InventoryList.svelte";
import Home from "./Home.svelte";
import SummaryScreen from "./SummaryScreen.svelte";
import Footer from "./Footer.svelte";
let Items = [
	{productName: "MICHELIN XTA2 ENRG 295/75R22.5", productNumber: "M44841", custom: false, itemid: 1, expectedQty: 32},
	{productName: "MICHELIN XLINE 2 295/75R22.5", productNumber: "M22313", custom: false, itemid: 2, expectedQty: 12},
	{productName: "MICHELIN TIRE THING 295/75R22.5", productNumber: "M82141", custom: false, itemid: 3, expectedQty: 15},
	{productName: "MICHELIN OTHER TIRE 295/75R22.5", productNumber: "M34581", custom: false, itemid: 4, expectedQty: 4},
	{productName: "MICHELIN TIRE TWO 295/75R22.5", productNumber: "M22384", custom: true, itemid: 5},
	{productName: "MICHELIN TIRE TWO 295/75R22.5", productNumber: "M22384", custom: true, itemid: 6},
	{productName: "MICHELIN TIRE TWO 295/75R22.5", productNumber: "M22384", custom: true, itemid: 7},
	{productName: "MICHELIN XTA2 ENRG 295/75R22.5", productNumber: "M44841", custom: false, itemid: 8, expectedQty: 32},
	{productName: "MICHELIN XLINE 2 295/75R22.5", productNumber: "M22313", custom: false, itemid: 9, expectedQty: 12},
	{productName: "MICHELIN TIRE THING 295/75R22.5", productNumber: "M82141", custom: false, itemid: 10, expectedQty: 15},
	{productName: "MICHELIN OTHER TIRE 295/75R22.5", productNumber: "M34581", custom: false, itemid: 11, expectedQty: 4},
	{productName: "MICHELIN TIRE TWO 295/75R22.5", productNumber: "M22384", custom: true, itemid: 12},
	{productName: "MICHELIN TIRE TWO 295/75R22.5", productNumber: "M22384", custom: true, itemid: 13},
	{productName: "MICHELIN TIRE TWO 295/75R22.5", productNumber: "M22384", custom: true, itemid: 14}
];

let AuditHeader = new Object({
	storeid: 779, 
	starttime: new Date("January 17, 2020 13:12:00"), 
	auditid: 1,
	status: "Pending",
	totalitems: 43,
	totalexpectedqty: 447,
	iscomplete: false,
	title: "tires"
});

let view = "home";

const navToView = (newview) => {
	view = newview;
}

</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.gstatic.com">
	<link href="https://fonts.googleapis.com/css2?family=Fira+Sans+Extra+Condensed:ital,wght@0,400;0,700;1,900&display=swap" rel="stylesheet">
</svelte:head>
<div>
	<Header />
	{#if view == "audit"}
		<InventoryList 
			navToView={navToView}
			InventoryItems={Items}
			AuditHeader={AuditHeader}
		/>
	{/if}
	{#if view == "summary"}
		<SummaryScreen />
	{/if}
	{#if view == "home"}
		<Home 
			storeid = 779
		/>
	{/if}
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
			width: auto;
		}
	}
	div{
		display: grid;
		height: 100vh;
		grid-template-rows: auto 1fr auto;
	}
</style>