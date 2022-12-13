<script lang="ts">
    import { onMount } from "svelte";
    import { fade, fly } from "svelte/transition";
    import Nav from "./lib/Nav.svelte";

    let openedModal: boolean = false
</script>

<div id="superheader">
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
</div>
<div id="bodier">
    <div id="row">
        <div id="significato">
            <span>
                <div id="h6">
                    <li><strong>Che cos'è la Povertà?</strong></li>
                    <a href="#significato">
                        <input type="checkbox" bind:checked={openedModal}>
                    </a>
                </div>
                <img src="poverta.png" alt="img sulla poverta">
                <div id="definizione">
                    La povertà è una condizione in cui una persona o un gruppo di persone non ha accesso a 
                    risorse sufficienti per soddisfare i loro bisogni di base, come cibo, acqua,
                    alloggio, vestiti e cure mediche.
                </div>
            </span>
        </div>
    </div>
    <div id="column">
        {#if openedModal == false}
            <div id="contTipi" in:fly={{ x: 100, duration: 300 }} out:fly={{ x: -100, duration: 300 }}>
                <hgroup>
                    <h4 style="margin-top: 1rem;">Tipi di Povertà</h4>
                    <p>
                        Ci sono diversi tipi di povertà, tra cui la povertà assoluta, la povertà relativa e la povertà multidimensionale. La povertà assoluta si riferisce a una situazione in cui una persona non ha accesso ai beni e servizi di base, come cibo, acqua, alloggio e cure mediche. La povertà relativa, invece, si riferisce a una situazione in cui una persona non può permettersi di partecipare pienamente alla vita sociale e culturale della propria comunità a causa del suo basso reddito rispetto agli altri membri della comunità. La povertà multidimensionale, infine, si riferisce a una situazione in cui una persona è priva di diverse forme di benessere, come l'istruzione, la salute e l'accesso ai servizi pubblici.
                    </p>
                </hgroup>
            </div>
        {:else}
            <div id="contTipi" in:fly={{ x: -100, duration: 300 }} out:fly={{ x: 100, duration: 300 }}>
                <hgroup>
                    <h4 style="margin-top: 1rem;">Cause della Povertà</h4>
                    <p>
                        Le cause della povertà possono essere diverse, date non solo dallo sviluppo economico di un paese ma anche dagli eventi e fatti che si verificano nel mondo. I conflitti, la mancanza di risorse, le catastrofi naturali sono tutti fattori che possono causare la povertà.
                        Tra le fonti principali troviamo sicuramente le possibilità economiche di un paese: ad esempio nelle zone centrali dell’Africa, le istituzioni difficilmente hanno la possibilità di garantire le risorse necessarie per costruire infrastrutture che forniscono acqua pulita o servizi medico sanitari di qualità.
                        I paesi con un reddito più alto hanno maggiori opportunità di mettere a disposizione dei cittadini beni di prima necessità, posti di lavoro, borse di studio per l’istruzione e molti altri vantaggi che aiutano a condurre una vita qualitativamente migliore.
                        La guerra, un’altra delle maggiori cause della povertà nel mondo, è purtroppo una costante che alcune popolazioni sono costrette a sopportare ogni giorno. Ci sono guerre che si protraggono da anni e anni e che continuano ad indebolire il paese e a rallentare il suo sviluppo economico.
                        È passato un mese dall’inizio della guerra in Ucraina per mano della Russia di Putin e gli effetti sono stati avvertiti fin da subito: le pesanti sanzioni che sono state imposte dalla Nato e dall’Unione Europea, le spese di guerra e l’utilizzo di risorse naturali come gas e petrolio porteranno la Russia ad un abbassamento del PIL del 15% nel corso di quest’anno.
                        Molte di queste spese sono state riversate sulle spalle della popolazione russa che si è trovata a spendere il 14% in più per comprare prodotti base, come zucchero e grano.
                        Dall’altra parte, la maggioranza di cittadini ucraini è caduta in povertà: la guerra li ha costretti a scappare e abbandonare tutto, perdere la casa ed ogni tipo di bene, primario o accessorio che fosse.
                    </p>
                </hgroup>
                <hgroup>
                    <h4 style="margin-top: 1rem;">Come raggiungere il "SDG-1"</h4>
                    <p>
                        Per raggiungere questo obiettivo, è necessaria cooperazione. Questo ruolo vede protagonisti gli stati, delle associazioni di questi, ma anche il cittadino nel suo piccolo. L’azione del singolo paese riguardo questa tematica, è legata alla politica, infatti le scelte prese per combattere queste situazioni sono valide solo per quel particolare stato. Portando esempio dell’Italia, possiamo dire che lo Stato mette a disposizione sussidi e aiuti economici per chi vive una condizione di indigenza. Altre forme di aiuto vengono fornite anche dall’associazionismo sia cattolico, che laico, come ad esempio la Caritas, che solo nel 2021 quasi 2.800 centri hanno effettuato oltre 1,5 milioni di interventi, per poco meno di 15 milioni di euro, con un aumento del 7,7% delle persone che hanno chiesto aiuto rispetto all'anno precedente. Sono numerose anche le raccolte fondi, che a livello nazionale, aiutano circa il 2,7% della popolazione in situazioni di povertà. Per quanto riguarda invece e le associazioni di stati, come per esempio ONU, Oxfam, Unicef. Queste svolgono un ruolo fondamentale nella battaglia mondiale rispetto questo tema. l’ONU per esempio nel 2015 ha dato vita ad un programma di azione per combattere i problemi mondiali riguardanti l’uomo, il pianeta e la prosperità. Riguardo ad associazioni non governative potremmo citare Oxfam, un movimento di milioni di persone che lottano contro le disuguaglianze per porre fine alla povertà. Adoperano in 87 paesi e collaborano con circa 4 mila partner. Le azioni invece che il cittadino in prima persona può fare sono ad esempio fare volontariato, quindi aderire ad associazioni che aiutano la gente che ha bisogno. Oppure donare, cose da mangiare piuttosto che sprecarle, donare giocattoli, vestiti.

                    </p>
                </hgroup>
            </div>
        {/if}
    </div>
</div>
<div id="grafici">
    <iframe src="https://worldpoverty.io/" frameborder="0" title="World Data Lab"></iframe>
</div>

<style>

    #grafici {
        width: 100%;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    #grafici iframe {
        width: 95%;
        height: 90%;
        background-color: white;
    }

    a {
        text-decoration: none;
    }

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
        grid-template-columns: 20% 20% 20% 20%;
        grid-template-rows: 50% 50%;
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

    #significato span #h6 {
        margin: 0px;
        display: flex;
        justify-content: space-between;
    }

    #significato span #h6 li {
        list-style-type: none;
    }

    #definizione {
        color: var(--muted-color);
    }

    #contTipi {
        width: 90%;
        height: 90%;
        border-radius: 1rem;
        background-color: rgb(240, 240, 240);
        display: flex;
        overflow-x: scroll;
        scroll-snap-type: x mandatory;
    }

    #contTipi hgroup {
        min-width: 100%;
        height: 100%;
        margin: 0px;
        overflow-y: scroll;
        scroll-snap-align: center;
    }

    #contTipi hgroup::-webkit-scrollbar {
        width: 0px;
    }

    #contTipi hgroup h4 {
        padding: 3rem;
        padding-bottom: 0px;
        margin: 0px;
    }

    #contTipi hgroup p {
        padding: 3rem;
        padding-top: 0.8rem;
        text-align: start;
        margin: 0px;
    }

    @media screen and (max-width: 900px) {
        #contTipi hgroup p {
            font-size: medium;
            padding: 1.5rem;
            padding-top: 0px;
        }

        #contTipi hgroup h4 {
            padding: 1.5rem;
            margin-top: 0px !important;
        }

        #header {
            flex-direction: column-reverse;
        }

        #header > div {
            width: 90%;
            aspect-ratio: 1;
        }

        #bodier {
            grid-template-columns: calc(100% / 3) calc(100% / 3) calc(100% / 3);
            grid-template-rows: calc(100% / 7) calc(100% / 7) calc(100% / 7) calc(100% / 7) calc(100% / 7) calc(100% / 7) calc(100% / 7);
            grid-template-areas: 
            "a a a"
            "a a a"
            "a a a"
            "a a a"
            "a a a"
            "b b b"
            "b b b";
        }

        #significato span #h6 {
            display: flex;
            align-items: center;
            margin: 0px;
            height: 20%;
            padding: 0.5rem;
            padding-left: 0px;
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
            justify-content: center;
        }

        #definizione {
            height: 80%;
            display: flex;
            align-items: center;
            font-size: calc(4vw);
        }
    }
</style>