<script>

    import {createEventDispatcher} from 'svelte';

    const dispatch = createEventDispatcher();

    let recherche = "";

    function rechercheFunc(){
        // console.log(recherche);
        dispatch('recherche-poke', {txt: recherche})
        recherche = "";
    }

</script>

<form class="form-recherche" on:submit|preventDefault={rechercheFunc}>

    <label for="recherche">Cherchez un pokémon</label>
    <input bind:value={recherche} type="text" id="recherche" placeholder="Recherchez un pokémon">

    <button type="submit">Recherche</button>


</form>

<style>

    .form-recherche {
        margin: 200px auto 50px auto;
        max-width: 1100px;
        width: 100%;
        padding: 0 50px;
        /* background: crimson; */
        display: flex;
        align-content: center;
        flex-direction: column;
    }
    .form-recherche input, .form-recherche label  {
        max-width: 1100px;
        width: 100%;
    }
    .form-recherche label {
        font-size: 25px;
        border: none;
        padding: 10px 0px;
    }
    .form-recherche input {
        font-size: 20px;
        padding: 20px;
        background: rgb(240,197,240);
    }
    form button {
        padding: 15px 30px;
        background: violet;
        border: none;
        outline: none;
        cursor: pointer;
        margin-top: 5px;
        font-size: 18px;
        margin-right: auto;
    }
</style>