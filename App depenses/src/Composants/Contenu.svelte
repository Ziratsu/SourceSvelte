<script>

    import FormDepense from './FormDepense.svelte'
    import CarteDepense from './CarteDepense.svelte'
    import {v4 as uuidv4} from 'uuid'

    let tableauCartes = [

        {
            id: uuidv4(),
            nom: 'Courses',
            montant: 300
        },
        {
            id: uuidv4(),
            nom: 'Loisirs',
            montant: 150
        },
        {
            id: uuidv4(),
            nom: 'Lecture',
            montant: 100
        }
    ]

    $: total = tableauCartes.reduce((acc, curr) => {

       return acc += curr.montant;
  

    }, 0)
    

    function ajoutDepense(event){

        let nvObj = {id: uuidv4(), nom: event.detail.nom, montant: event.detail.montant}

        tableauCartes = [...tableauCartes, nvObj]

    }

    function suppressionCarte(event){

        tableauCartes = tableauCartes.filter(item => item.id !== event.detail.id)

    }

</script>

<div class="container">

    
    <FormDepense on:nv-depense={ajoutDepense} />

    <h2 class="my-4">Total des dépenses :  {total}</h2>

    {#each tableauCartes as depense (depense.id)}

        <CarteDepense 
        on:suppr-element={suppressionCarte}
        id={depense.id}
        nom={depense.nom}
        montant={depense.montant}
         />

    {/each}
</div>