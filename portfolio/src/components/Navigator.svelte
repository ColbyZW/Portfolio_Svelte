<script>
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    function navigate(event) {
        console.log(event);
        dispatch("message", {
            target: event.target.id,
        });
    }
</script>

<nav id="navigator_wrapper">
    <div id="navigator">
        <p id="navigator_header">More Info</p>
        <button on:click={navigate} id="about_button">About Me</button>
        <button on:click={navigate} id="project_button">Projects</button>
    </div>
</nav>

<style>
    button {
        text-decoration: none;
        color: aliceblue;
        display: block;
        margin-bottom: 1rem;
        background-color: transparent;
        border: 0;
        font-size: 1rem;
        font-family: "Courier New", Courier, monospace;
        margin: 0;
        padding: 0;
    }
    button:hover {
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
    }

    @media only screen and (min-width: 768px) {
        button {
            margin-bottom: 1rem;
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
