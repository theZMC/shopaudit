<script>
export let Info;
export let navToView;

let showinfo = false;

const toggleInfo = () => {
    showinfo = !showinfo;
}
</script>

<div class="root">
    <div>
        <button on:click={() => navToView("home")}>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm.707-10.293a1 1 0 00-1.414-1.414l-3 3a1 1 0 000 1.414l3 3a1 1 0 001.414-1.414L9.414 11H13a1 1 0 100-2H9.414l1.293-1.293z" clip-rule="evenodd" />
            </svg>
        </button>
        <h3>
            {Info.title}
        </h3>
        <h3>{Info.starttime.toLocaleDateString('en-US')}</h3>
        <h3>Store {Info.storeid}</h3>
    </div>
    {#if showinfo}
        <ul>
            <li>Total Items: <span>{Info.totalitems}</span></li>
            <li>Inventory Quantity: <span>{Info.totalexpectedqty}</span></li>
            <li>Start Time: <span>{Info.starttime.toLocaleTimeString('en-US')}</span></li>
            <li>Status: <span>{Info.status}</span></li>
        </ul>
    {/if}
    {#if showinfo}
    <span on:click={toggleInfo}>Hide Audit Info</span>
    {:else}
    <span on:click={toggleInfo}>Show Audit Info</span>
    {/if}
</div>

<style>
    div.root{
        color: #333333;
        padding: 1rem;
        text-shadow: 0px 1px 0px #eeeeee77;
        user-select: none;
        display: flex;
        flex-direction: column;
    }
    div.root > div{
        display: flex;
        padding: 0;
        border-bottom: 1px solid #444444;
    }
    div > div > h3{
        font-size: 1.6rem;
        font-weight: bolder;
        padding-bottom: .7rem;
        flex-grow: 1;
        align-self: flex-end;
        text-align: right;
    }
    div.root > div > button{
        background: none;
        border: none;
        margin-bottom: 0;
        padding-bottom: .5rem;
    }
    div.root > div > button > svg{
        min-width: 2rem;
    }
    div.root > div > button:hover{
        cursor: pointer;
        color: #bbb;
    }
    div > div > h3:first-of-type{
        font-size: 2rem;
        margin-right: auto;
        text-align: left;
    }
    div > div > h3:last-of-type{
        text-align: right;
        margin-left: auto;
    }
    div > ul{
        font-size: 1.4rem;
        padding: 1rem 0 0 0;
        border-top: 1px solid #eeeeee77;
        font-weight: bold;
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: .5rem 2rem;
    }
    div > ul > li{
        display: flex;
        justify-content: space-between;
    }
    div > span{
        text-align: center;
        margin: 1rem auto 0 auto;
        font-weight: bolder;
        text-transform: uppercase;
        font-size: 1.2rem;
        cursor: pointer;
    }
</style>