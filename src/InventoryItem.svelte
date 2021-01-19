<script>
    export let handleDeleteItem;
    export let productName;
    export let productNumber;
    export let custom;
    export let itemid;
    export let expectedQty;
    let count = 0;
    const countUp = () => { if(count < 1000) count++} ;
    const countDown = () => { if(count) count-- };
</script>

<div>
    <button on:click|preventDefault={countDown}>
        <svg class="w-6 h-6" fill="none" stroke="white" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 12H4"></path>
        </svg>
    </button>
    <p>
        {#if productNumber}
            <span>{productNumber}</span>
        {/if}
        {#if !custom}
            <span class="expected-qty">
                BOH<br />
                <span>{expectedQty}</span>
            </span>
        {/if}
        {#if custom}
            <span class="custom-delete">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" on:click={() => handleDeleteItem(itemid)}>
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
                </svg>
            </span>
        {/if}
        {#if productName}
            <span>{productName}</span>
        {/if}
    </p>
    <input 
        type="number" 
        bind:value={count}
    />
    <button on:click|preventDefault={countUp}>
        <svg fill="none" stroke="white" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"></path>
        </svg>
    </button>
</div>

<style>
    input[type=number]::-webkit-inner-spin-button {
        -webkit-appearance: none;
    }
    div{
        display: grid;
        background: linear-gradient(#eeeeee, #dddddd);
        grid-template-columns: auto 1fr auto auto;
        grid-gap: .5rem;
        border: 1px solid #666;
        border-top: 1px solid #fff;
        border-bottom: 3px solid #666;
        border-radius: .5rem;
        margin: 0 .5rem;
    }
    div > button{
        line-height: 1rem;
        font-size: 5rem;
        font-weight: bolder;
        border: none;
        outline: none;
        margin: 0;
        color: white;
        text-shadow: 0px 2px 2px rgba(0,0,0,.5);
        margin: 5px;
        margin-top: 2px;
        box-shadow: 0px 2px 4px rgba(90,90,90,.7);
        padding: 1rem;
        border-radius: .5rem;
    }
    div > button > svg{
        width: 2rem;
        margin: 0;
    }
    div > button:first-of-type{
        background: rgb(156,0,0);
        border-bottom: 2px solid rgb(89,0,0);
        border-top: 1px solid rgb(244,0,0);
    }
    div > button:last-of-type{
        background: rgb(0,134,19);
        border-bottom: 2px solid rgb(0,85,8);
        border-top: 1px solid rgb(0,210,25);
    }
    div > button:active{
        border-bottom-width: 1px;
        margin-top: 3px;
        box-shadow: 0px 1px 3px rgba(90,90,90,.5);
    }
    div > p{
        margin: 1rem 0;
        font-size: 1.6rem;
        display: flex;
        flex-direction: column;
        place-content: center;
        font-weight: bolder;
        font-size: 1.2rem;
        justify-content: space-around;
        position: relative;
        padding-right: 2.8rem;
        user-select: none;
    }
    div > input{
        font-weight: bolder;
        font-size: 3rem;
        margin: 0;
        padding: 0;
        min-width: 4rem;
        max-width: 7rem;
        text-align: center;
        margin: .8rem 0;
        border-radius: .5rem;
        box-shadow: inset 0px 1px 2px rgba(60,60,60,.2);
        background: linear-gradient(#fff, #eee);
        border-bottom: 1px solid #fff;
    }
    div > input:focus{
        outline: none;
    }
    div > p > span:first-of-type{
        display: block;
        font-weight: bolder;
        color: #676767;
        font-size: 1.8rem;
        text-transform: uppercase;
    }
    div > p > span:last-of-type{
        display: block;
        font-weight: bolder;
        font-size: 1.5rem;
        overflow: ellipsis;
        line-clamp: 2;
        text-transform: uppercase;
    }
    div > p > span:only-child{
        font-size: 1.8rem;
        color: black;
    }
    div > p > span.custom-delete{
        float: right;
        width: 1.5rem;
        position: absolute;
        right: 0;
    }
    div > p > span.custom-delete > svg{
        width: 2rem;
        float: right;
        padding:.25rem;
        background: #eee;
        border-top: 1px solid #fff;
        border-bottom: 1px solid #aaa;
        border-radius: .25rem;
        color: #333;
        box-shadow: 0px 1px 2px #00000044;
    }
    div > p > span.custom-delete > svg:hover{
        cursor: pointer;
        background: #f9f9f9;
    }
    div > p > span.custom-delete > svg:active{
        cursor: pointer;
        background: #f9f9f9;
        box-shadow: 0px 1px 1px #00000022;
        border-bottom: none;
        margin-top: 1px;
    }
    div > p > span.expected-qty{
        position: absolute;
        color: #aaa;
        font-size: 1rem;
        padding: .4rem 0;
        top: 0;
        right: 0;
        text-align: center;
        min-width: 2.5rem;
    }
    div > p > span.expected-qty > span{
        font-size: 1.6rem;
    }
</style>