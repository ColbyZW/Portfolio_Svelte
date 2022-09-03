<div id="javabot_container">
    <div id="javabot_content">
        <p style="text-align: center;">JavaBot</p>
        <div id="javabot_flex">
            <p>
            A discord bot written with the JDA wrapper/library. Integrated with
            MongoDB to store users and keep track of the money earned on the
            server. Commands are all prefixed with a "!".</p>
            <a id="github_logo" href="https://github.com/ColbyZW/JavaBot" target="_blank"><img alt="github logo" src="/src/assets/github.png"></a>
        </div>
    </div>
</div>

<style>
    @keyframes easeIn {
        0% {
            transform: scale(0.35);
        }
        100% {
            transform: scale(1);
        }
    }
    #javabot_container {
        animation: 300ms ease-in-out 0s 1 easeIn;
        background-color: aliceblue;
        border-radius: 5%;
        padding: 1.5rem;
        margin: 1rem;
    }
    #javabot_content {
        font-size: 1.1rem;
    }
    #javabot_flex {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    #github_logo {
        justify-self:flex-end;
    }
    @media only screen and (max-width: 768px) {
        #javabot_container {
            max-width: 80vw;
            min-width: 90vw;
            max-height: 55vh;
        }
    }
    @media only screen and (min-width: 768px) {
        #javabot_container {
            max-width: 50vw;
            max-height: 40vh;
            min-width: 50vw;
        }
    }
</style>
