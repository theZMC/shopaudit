<script></script>
<footer>
    <div>
        <button>Reset</button>
        <button>Preview</button>
        <button>Finalize</button>
    </div>
</footer>
<style>
    footer{
        background: linear-gradient(rgb(255,128,0), rgb(220,110,0));
        position: relative;
        box-shadow: 0px 0px 5px #00000077;
    }
    footer > div{
        display: flex;
        flex-direction: row;
        gap: 1rem;
        justify-content: space-between;
    }
    footer > div > button{
        margin: 1rem;
        font-size: 1.4rem;
        font-weight: bold;
        text-transform: uppercase;
        border-radius: .5rem;
        outline: none;
        border: none;
        padding: .5rem 1rem;
        flex-basis: auto;
        background: linear-gradient(#eeeeee,#dddddd);
        border-top: 1px solid #ffffff;
        border-bottom: 2px solid #bbbbbb;
        box-shadow: 0px 2px 2px rgb(0,0,0,.2);
    }
    footer > div > button:active{
        margin-top: calc(1rem + 1px);
        border-bottom-width: 1px;
        box-shadow: 0px 1px 1px rgb(0,0,0,.2);
    }
    footer > div > button:first-of-type{
        align-self: left;
    }
	@media only screen and (min-width: 600px){
        footer > div{
            max-width: 600px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
        }

    }
</style>