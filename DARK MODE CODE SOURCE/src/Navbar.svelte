<script>

import {onMount} from 'svelte';


let toggleMenu = false;

function toggleMenuRes(){
    toggleMenu = !toggleMenu;
}

function resetMenu(){
    toggleMenu = false;
}

onMount(() => {

    const mediaListener = window.matchMedia("(max-width: 650px)");

    mediaListener.addListener(resetMenu)

})
</script>

<nav>

    <div on:click={toggleMenuRes} class="logo">
        <div>&#9776;</div>
    </div>

    <ul class={toggleMenu ? "liste-nav visible" : "liste-nav"}>
    
        <li class="item-nav">
            <a href="#">Lorem</a>
        </li>
        <li class="item-nav">
            <a href="#">Lorem</a>
        </li>
        <li class="item-nav">
            <a href="#">Lorem</a>
        </li>
        <li class="item-nav">
            <a href="#">Lorem</a>
        </li>
        <li class="item-nav">
            <a href="#">Lorem</a>
        </li>
        <li class="item-nav">
            <a href="#">Lorem</a>
        </li>

    </ul>

</nav>


<style>

    nav {
        height: 70px;
        width: 100%;
        background: #333;
        position: relative;
    }
    .logo {
        color: #fff;
        font-size: 40px;
        position: absolute;
        left: 10px;
        top: 5px;
        display: none;
    }
    .liste-nav {
        list-style-type: none;
        display: flex;
        justify-content: center;
        height: 100%;
        align-items: center;
    }
    
    .liste-nav li a {
        color: #f1f1f1;
        text-decoration: none;
        margin: 0 10px;
        font-size: 22px;
    }

    @media only screen and (max-width: 650px){
        .logo {
            display: block;
        }
        .liste-nav {
            flex-direction: column;
            position: relative;
            top: 70px;
            display: none;
        }
        .liste-nav.visible {
            display: block;
        }
        .item-nav {
            width: 100vw;
            background: #333;
            text-align: center;
            padding: 10px 0;
        }
    }

</style>