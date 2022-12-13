<script lang="ts">
    import { onMount } from "svelte";
    
    let fullBTN: HTMLElement
    let fullscreen = ["in.svg", "out.svg"]
    let fullscreenSrc: string = ""
    let bool = false

    onMount(() => {
        let ciao: HTMLElement = document.querySelector("#app")
        ciao.querySelector("#button").addEventListener("click", () => {
            ciao.scroll({
                top: (document.querySelector("#grafici") as HTMLElement).offsetTop
            })
        })
    })

    const updateSrc = () => {
        if(bool) {
            fullscreenSrc = fullscreen[1]
            document.body.requestFullscreen()
        } else {
            fullscreenSrc = fullscreen[0]
            document.exitFullscreen()
        }

        bool = !bool

        fullBTN.style.backgroundImage = `url(${fullscreenSrc})`
    }

</script>

<nav>
    <ul>
        <li>
            <slot name="titolo"></slot>
        </li>
    </ul>
    <ul>
        <li>
            <div id="full" bind:this={fullBTN} on:keydown={() => {}} on:click={() => updateSrc()}></div>
        </li>
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
        padding: 0px;
        height: 100%;
        aspect-ratio: 1;
        display: flex;
        justify-content: flex-start;
        align-items: center;
    }

    #full {
        height: 100%;
        aspect-ratio: 1;
        background-position: center center;
        background-size: 60% 60%;
        background-image: url(in.svg);
    }
</style>