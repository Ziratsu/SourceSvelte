<script>

    export let name;
    export let pic;

</script>

<div class="carte">
    <p class="nom">{name}</p>
    <img src={pic} alt="pokemon">
</div>

<style>

    .carte {
        width: 300px;
        height: 200px;
        background: rgba(238,130,238,0.23);
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin: 5px;
    }
    .carte img {
        width: 100px;
    }
    .carte p {
        font-size: 25px;
    }

</style>