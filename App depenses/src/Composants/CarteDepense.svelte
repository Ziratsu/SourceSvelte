<script>
    import {createEventDispatcher} from 'svelte'

    export let nom;
    export let montant;
    export let id;

    const dispatch = createEventDispatcher();

    function envoyerSuppression(){
        dispatch('suppr-element', {id: id})
    }

</script>

<div class="card my-3">
    <div class="card-body">
        <h3>{nom}</h3>
        <p>{montant}</p>
        <i class="trash" on:click={envoyerSuppression}>
            <img src="ressources/trash-solid.svg" alt="">
        </i>
    </div>
</div>

<style>

    .card {
        position: relative;
    }
    .card h3 {
        font-size: 35px;
    }
    .card p {
        font-weight: 300;
        font-size: 25px;
    }
    i {
        cursor: pointer;
    }
    i img {
        width: 30px;
    }
    .trash {
        position: absolute;
        top: 10px;
        right: 20px;
    }

</style>