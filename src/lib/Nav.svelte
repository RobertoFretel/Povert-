<script lang="ts">
    import { onMount } from "svelte";
    
    onMount(() => {
        let ciao: HTMLElement = document.querySelector("#app")
        ciao.querySelector("#button").addEventListener("click", () => {
            ciao.scroll({
                top: (document.querySelector("#grafici") as HTMLElement).offsetTop
            })
        })
    })
</script>

<nav>
    <ul>
        <li>
            <slot name="titolo"></slot>
        </li>
    </ul>
    <ul>
        <li>
            <a id="button">
                <slot name="button"></slot>
            </a>
        </li>
    </ul>
</nav>

<style>
    nav {
        width: 100%;
        height: 10vh;
        display: flex;
        justify-content: space-between;
        background: linear-gradient(
            to bottom, rgba(0, 0, 0, .25), rgba(0, 0, 0, .0)
        );
    }

    nav ul, nav ul li {
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 0px;
        padding: 0px;
    }

    nav ul:first-child {
        padding-left: 1rem;
    }

    nav ul:last-child {
        aspect-ratio: 1.5;
    }

    nav ul:last-child li {
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
    }

    li a {
        height: 100%;
        aspect-ratio: 1;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>