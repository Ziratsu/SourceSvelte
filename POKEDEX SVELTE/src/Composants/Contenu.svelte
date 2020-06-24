<script>

    import BarreRecherche from './BarreRecherche.svelte'
    import Carte from './Carte.svelte'
    import {v4 as uuidv4} from 'uuid';

    let allPokemon = [];
    let tableauFin = [];

    function fetchPokemonBase(){

        fetch('https://pokeapi.co/api/v2/pokemon?limit=151')
        .then(reponse => reponse.json())
        .then(function(allPoke){
            // console.log(allPoke);

            allPoke.results.forEach(function(pokemon){
                fetchPokemonComplet(pokemon)
            })
            
        })
        

    }
    fetchPokemonBase()


    function fetchPokemonComplet(pokemon){

        let objPokemonFull = {};
        let url = pokemon.url;
        let nameP = pokemon.name;

        fetch(url)
        .then(reponse => reponse.json())
        .then(function(pokeData){

            // console.log(pokeData);
            
            objPokemonFull.pic = pokeData.sprites.back_default;


            fetch(`https://pokeapi.co/api/v2/pokemon-species/${nameP}`)
            .then(reponse =>  reponse.json())
            .then(function(pokeData){
                // console.log(pokeData);
                objPokemonFull.name = pokeData.names[4].name;

                allPokemon.push(objPokemonFull);
            })
            .then(() => {
                // console.log(allPokemon);
                tableauFin = allPokemon.slice(0,20)
                allPokemon = allPokemon;
            })

        })

    }



function goRecherche(event){
    // console.log(event.detail.txt);

    let contenuRecherche = event.detail.txt;

    tableauFin = allPokemon.filter(el => el.name.includes(contenuRecherche))
    
}


</script>


<BarreRecherche on:recherche-poke={goRecherche} />

<div class="contenu">
 
    {#each tableauFin as pokemon (uuidv4())}
        <Carte name={pokemon.name} pic={pokemon.pic} />
    {/each}

</div>


<style>

    .contenu {
        max-width: 1400px;
        width: 95%;
        padding: 0 50px;
        margin: 0 auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        /* background: orange; */
    }

</style>