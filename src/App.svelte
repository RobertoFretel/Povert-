<script lang="ts">
    import { onMount } from "svelte";
    import Nav from "./lib/Nav.svelte";
</script>

<Nav>
    <strong style="font-size: 1.5rem;" slot="titolo">Povertà</strong>
    <svg slot="button" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 41.8 31.3"><g><path class="fillSecond" fill="#E8482B" d="M34.2,29.8l7.5-18c0.5-1.2-0.8-2.4-1.9-1.8c-2.1,1-4.8,1.9-7.7,1.9c-3,0-5.7-0.9-7.8-1.9   c-1.2-0.6-2.4,0.6-1.9,1.8l7.5,18C30.6,31.8,33.4,31.8,34.2,29.8z"></path><path class="fillFirst" fill="#010202" d="M7.6,11.3l-7.5,18c-0.5,1.2,0.8,2.4,1.9,1.8c2.1-1,4.8-1.9,7.7-1.9c3,0,5.7,0.9,7.8,1.9   c1.2,0.6,2.4-0.6,1.9-1.8l-7.5-18C11.2,9.3,8.4,9.3,7.6,11.3z"></path><path class="fillSecond" fill="#E8482B" d="M35.7,3.7C35.7,1.6,34,0,32,0c-2.1,0-3.7,1.7-3.7,3.7c0,2.1,1.7,3.7,3.7,3.7C34.1,7.4,35.7,5.8,35.7,3.7z"></path><path class="fillFirst" fill="#010202" d="M13.6,3.7c0-2.1-1.7-3.7-3.7-3.7C7.8,0,6.2,1.7,6.2,3.7c0,2.1,1.7,3.7,3.7,3.7S13.6,5.8,13.6,3.7z"></path></g></svg>
</Nav>

<div id="header">
    <div id="image"></div>
    <div id="titlecont">
        <div id="bubble">
            <span id="h1">Educazione Civica 2022/2023</span>
        </div>
    </div>
</div>
<div id="bodier">
    <div id="row">
        <div id="significato">
                <span>
                    <h6>Che cos'è la Povertà?</h6>
                    <img src="poverta.png" alt="img sulla poverta">
                    <div id="definizione">
                        La povertà è una condizione in cui una persona o un gruppo di persone non ha accesso a 
                        risorse sufficienti per soddisfare i loro bisogni di base, come cibo, acqua,
                        alloggio, vestiti e cure mediche.
                    </div>
                </span>
        </div>
    </div>
    <div id="column"></div>
</div>

<style>
    svg {
        width: 60%;
        height: 60%;
        object-fit: contain;
    }

    #header {
        width: 100%;
        height: 90vh;
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        background-size: 100% 100%;
    }

    #header > div {
        width: 40%;
        aspect-ratio: 1;
    }

    #image {
        background-image: url(Webinar-pana.svg);
        background-repeat: no-repeat;
        background-size: 100% 100%;
    }

    #titlecont {
        display: flex;
        justify-content: center;
        align-items: flex-end;
        aspect-ratio: none;
        height: 40%;
    }

    #bubble {
        max-width: 95%;
        max-height: 95%;
        white-space: pre-wrap;
        display: flex;
        justify-content: flex-end;
        align-items: flex-end;
    }

    #bubble #h1 {
        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif !important;
        font-size: 3rem;
        margin: 0px;
        font-weight: bold;
        color: rgb(240, 240, 240);
    }

    #bodier {
        width: 100%;
        height: 100vh;
        background-color: transparent;
        display: grid;
        grid-template-areas: 
        "a a a b b"
        "a a a b b";
        background: rgb(175, 175, 175);
    }

    #row {
        grid-area: b;
    }

    #column {
        grid-area: a;
    }

    #row, #column {
        display: flex;
        align-items: center;
        justify-content: center;
    } 

    #significato {
        position: relative;
        width: 90%;
        height: 90%;
        border-radius: 1rem;
        background-color: rgb(240, 240, 240);
    }

    #significato span {
        position: absolute;
        top: 50%;
        left: 50%;
        translate: -50% -50%;
        width: 80%;
        height: 90%;
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
    }

    #significato span h6 {
        margin: 0px;
    }

    @media screen and (max-width: 900px) {
        #header {
            flex-direction: column-reverse;
        }

        #header > div {
            width: 90%;
            aspect-ratio: 1;
        }

        #bodier {
            grid-template-areas: 
            "a a a"
            "a a a"
            "a a a"
            "b b b"
            "b b b";
        }

        #significato span h6 {
            display: flex;
            align-items: center;
            margin: 0px;
            height: 10%;
        }

        #significato span img {
            display: none;
        }

        #significato span {
            top: 50%;
            left: 50%;
            translate: -50% -50%;
            overflow: hidden;
            display: flex;
        }

        #definizione {
            height: calc(90% - 1rem);
            display: flex;
            align-items: center;
        }
    }
</style>