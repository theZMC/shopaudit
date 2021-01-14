<script>
    export let productName;
    export let productNumber;
    let count = 0;
    const countUp = () => { if(count < 1000) count++} ;
    const countDown = () => { if(count) count-- };
</script>

<div>
    <button on:click|preventDefault={countDown}>-</button>
    <p>
        <span>{productNumber}</span>
        {productName}
    </p>
    <input 
        type="number" 
        bind:value={count}
        max=999
    />
    <button on:click|preventDefault={countUp}>+</button>
</div>

<style>
    input[type=number]::-webkit-inner-spin-button {
        -webkit-appearance: none;
    }
    div{
        display: grid;
        background: #eeeeee;
        grid-template-columns: auto 1fr auto auto;
        grid-gap: 1rem;
        border-radius: 1rem;
        border: 1px solid #ccc;
    }
    div > button{
        min-width: 4rem;
        font-size: 4rem;
        padding: 0rem 2.5rem;
        font-weight: bolder;
        border: none;
        outline: none;
        margin: 0;
        color: white;
        text-shadow: 0px 2px 4px rgba(0,0,0,.5);
        padding-bottom: .6rem;
        margin: 5px;
        margin-top: 1px;
        box-shadow: 0px 4px 4px rgba(90,90,90,.7);
        border-radius: 1rem;
    }
    div > button:first-of-type{
        background: rgb(156,0,0);
        border-bottom: 4px solid rgb(89,0,0);
    }
    div > button:last-of-type{
        background: rgb(0,134,19);
        border-bottom: 4px solid rgb(0,85,8);
    }
    div > button:active{
        border-bottom-width: 2px;
        margin-top: 3px;
        box-shadow: 0px 2px 3px rgba(90,90,90,1);
    }
    div > p{
        margin: 1rem 0;
        font-size: 1.6rem;
        display: flex;
        flex-direction: column;
        place-content: center;
        font-weight: bolder;
        font-size: 1.8rem;
    }
    div > input{
        font-weight: bolder;
        font-size: 2.5rem;
        margin: 0;
        padding: 0;
        max-width: 6rem;
        text-align: center;
        margin: .8rem 0;
        border-radius: .5rem;
        box-shadow: inset 0px 0px 3px rgba(60,60,60,.2);
    }
    div > input:focus{
        outline: none;
    }
    div > p > span{
        display: block;
        font-weight: bolder;
        color: #888888;
        font-size: 1.4rem;
    }
</style>