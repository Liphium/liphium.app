<script lang="ts">
	import { onMount } from "svelte";    

    onMount(() => {

        const observer = new IntersectionObserver((entries) => {
            entries.forEach((entry) => {
                console.log("change")

                if(entry.isIntersecting) {
                    console.log("added");
                    entry.target.classList.add('appear');
                }
            });
        });
        document.querySelectorAll('.aos').forEach((el) => {
            observer.observe(el);
        });
    });
</script>

<div class="gradient">
    <div class="spacer-top">
        <img class="logo" src="/liphium.png" alt="Logo">
    </div>
    <p>It's time to <span class="colored">supercharge</span> your <span class="colored">message</span> app.</p>
</div>
<div class="description">
    <p class="readable">With Liphium I tried to create the a secure and safe place for me and my friends. If you like the approach we're taking be sure to join the alpha!</p>
</div>
<div class="spacer"></div>
<div class="description">
    <button class="secondary-action-button">Features</button>
    <button class="action-button">Join alpha</button>
</div>

<div class="spacer-big"></div>

<div class="center-maxwidth">

    <div class="row aos">
        <div class="desc">
            <span class="material-symbols">public</span>
            <p>Find new ways to interact with your friends</p>
            <p class="secondary">Get your entire friends group together with next level features for sharing your calls (Spaces).</p>
        </div>
        <div class="desc left">
            <span class="material-symbols">select_check_box</span>
            <p>No setup needed</p>
            <p class="secondary">Liphium has all the features you need to interact with your friends group, no matter how big. And it all works out of the box.</p>
        </div>
    </div>

    <div class="spacer-medium"></div>

    <div class="row aos">
        <div class="desc aos">
            <span class="material-symbols">lock</span>
            <p>Privacy by default</p>
            <p class="secondary">Everything you share on the app is 100% end-to-end encrypted so not even we can see what you are doing with your friends.</p>
        </div>
        <div class="desc aos">
            <span class="material-symbols">sell</span>
            <p>Servers are expensive</p>
            <p class="secondary">A free app just doesn't pay for the server infrastructure needed for our app. That's why there will be a price tag on some features, but that doesn't mean it'll be expensive.</p>
        </div>
    </div>

    <div class="spacer-medium"></div>

    <div class="row aos">
        <div class="desc aos">
            <span class="material-symbols">equalizer</span>
            <p>High quality voice calls</p>
            <p class="secondary">Get secure voice chat that is made for the modern area of voice calls. You shouldn't have to hear someone while they're not talking.</p>
        </div>
        <div class="desc aos">
            <span class="material-symbols">content_copy</span>
            <p>Share (large) files quicker</p>
            <p class="secondary">With Live Share you can instantly share files of any size without someone else having to wait for a message. Of course they have to accept first.</p>
        </div>
    </div>
</div>

<div class="spacer-big"></div>

<p class="header-small aos"></p>
<p class="header aos">Join the alpha</p>
<div class="spacer-big"></div>

<style lang="scss">

    .gradient {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 0 0 3rem 0;
        color: var(--text);
        font-family: "Inter";
        font-size: 60px;
        animation: background-move 10s ease infinite;
        background-clip: unset;
        background-repeat: no-repeat;
        
        p {
            text-align: center;
            width: 700px;
        }

        .colored {
            color: var(--accent);
        }
    }

    .header {
        font-size: 50px;
        color: var(--text);
        text-align: center;
        transition: transform 0.5s ease;
        transform: translateY(200px);
    }

    .header-small {
        font-size: 30px;
        color: var(--sec-text);
        text-align: center;
        transition: transform 0.5s ease;
        transform: translateY(200px);
    }

    .center-maxwidth {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        max-width: 1200px;
        margin: 0 auto;
    }

    .chat-stuff {
        background: var(--secondary);
        width: 400px;
        height: 300px;
    }

    .row {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        gap: var(--section-spacing);
        transition: transform 0.5s ease;
        gap: 100px;
        transform: translateY(200px);

        span {
            font-size: 50px;
            color: var(--accent);
        }

        .desc {
            display: flex;
            flex-direction: column;
            align-items: start;
            justify-content: start;
            text-align: start;
            width: 500px;
            gap: var(--section-spacing);
            font-size: 30px;
            color: var(--text);

            .secondary {
                color: var(--sec-text);
                font-size: var(--large-font);
                line-height: 1.5;
            }
        }
    }

    .spacer-top {
        display: flex;
        align-items: center;
        justify-content: center;
        background: radial-gradient(circle at center, var(--header-bg) 0%, var(--background) 100px), var(--background);
        padding: calc(var(--section-spacing) * 4) 0;
        height: 15vh;
    }

    .spacer {
        height: var(--section-spacing);
    }

    .spacer-medium {
        height: calc(var(--section-spacing) * 4);
    }

    .spacer-big {
        height: calc(var(--section-spacing) * 12);
    }

    .logo {
        min-width: 70px;
        width: 5%;
        margin-right: 1rem;
        color: var(--background);
    }

    .description {
        display: flex;
        justify-content: center;
        gap: var(--section-spacing);
        color: var(--text);
        text-align: center;

        p {
            max-width: 500px;
            font-size: var(--large-font);
        }
    }

</style>