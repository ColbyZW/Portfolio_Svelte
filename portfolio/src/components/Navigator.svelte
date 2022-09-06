<script>
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    function navigate(event) {
        dispatch("message", {
            target: event.target.id,
        });
    }
</script>

<nav id="navigator_wrapper">
    <div id="navigator">
        <p id="navigator_header">More Info</p>
        <a on:click={navigate} id="about_button">About Me</a>
        <a on:click={navigate} id="project_button">Projects</a>
        <a target="_blank" href="https://www.linkedin.com/in/Colby-Z-Wang">LinkedIn</a>
        <a target="_blank" href="https://www.github.com/ColbyZW">GitHub</a>
    </div>
</nav>

<style>
    a {
        text-decoration: none;
        color: aliceblue;
        display: block;
        margin-bottom: 1rem;
        background-color: transparent;
        border: 0;
        font-size: 1rem;
        font-family: "Courier New", Courier, monospace;
        padding: 0;
    }
    a:hover {
        text-decoration: underline;
        cursor: pointer;
    }
    #navigator {
        color: aliceblue;
        text-align: center;
        display: flex;
    }
    @media only screen and (max-width: 768px) {
        #navigator {
            flex-direction: row;
            width: 90vw;
            justify-content: space-evenly;
            margin-bottom: 2rem;
            margin-top: 1rem;
        }
        #navigator_header {
            display:none;
        }
        a {
            text-decoration: underline;
        }
    }

    @media only screen and (min-width: 768px) {
        a {
            margin-bottom: 0.6rem;
        }
        #navigator {
            flex-direction: column;
        }
        #navigator_header {
            font-size: 1.2rem;
            text-decoration: underline;
        }
        #navigator_wrapper {
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
    }
</style>
