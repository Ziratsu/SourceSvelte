<script>

    import storeData from './store/store.js'

    let toggleDarkLight;

    storeData.subscribe(value => {
        toggleDarkLight = value;
    })

    function toggleScreen(){
        storeData.set(!toggleDarkLight)
        console.log(toggleDarkLight);
        
    }

</script>

<button 
on:click={toggleScreen} 
class={toggleDarkLight ? "btn-toggle go-dark" : 'btn-toggle go-light'} 
type="button">
    {toggleDarkLight ? "Go dark" : "Go light"}
</button>

<style>

    .btn-toggle {
        width: 70px;
        height: 70px;
        border-radius: 50%;
        /* background: #333;
        color: #f1f1f1; */
        outline: none;
        position: absolute;
        top: 15px;
        right: 15px;
        cursor: pointer;
        transition: color 0.2s ease-in, background-color 0.2s ease-in;
    }

</style>