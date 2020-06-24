<script>

    import {createEventDispatcher} from 'svelte'

    const dispatch = createEventDispatcher();


    let objNvDep = {
        nom: '',
        montant: ''
    }

    function nouvelleDepense(){
        // console.log(objNvDep);

        dispatch('nv-depense', {nom: objNvDep.nom, montant: objNvDep.montant})

        objNvDep.nom = '';
        objNvDep.montant = '';
    }

</script>

<form class="mt-5" on:submit|preventDefault={nouvelleDepense}>

    <div class="form-group">
        <label for="depense" class="lead font-weight-bold">
            Nom de la dépense
        </label>
        <input bind:value={objNvDep.nom} type="text" id="depense" placeholder="Rentrez une nouvelle dépense" class="form-control">
    </div>

    <div class="form-group">
        <label for="montant" class="lead font-weight-bold">
            Montant
        </label>
        <input bind:value={objNvDep.montant} type="number" id="montant" placeholder="Montant de la dépense" class="form-control">
    </div>

    <button type="submit" class="btn btn-primary">Ajouter la dépense</button>

</form>