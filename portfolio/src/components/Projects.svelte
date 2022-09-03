<script>
import Javabot from "./Javabot.svelte";

    let project = undefined;
    function selectProject(event) {
        project = event.target.id
            ? event.target.id
            : event.target.parentElement.id;
    }
</script>

<main>
    <!-- Shows the expanded project card if one is selected -->
    {#if project}
        <div id="expanded_projects">
            <Javabot/>
        </div>
    {/if}

    <!-- Shows the project cards if we don't have a project selected -->
    {#if !project}
        <div id="project_wrapper">
            <div on:click={selectProject} id="java_bot" class="project_card">
                <p>JavaBot</p>
                <img
                    class="image"
                    alt="discord logo"
                    src="/src/assets/discordlogo.png"
                />
            </div>
            <div on:click={selectProject} id="reef_buddy" class="project_card">
                <p>Reef Buddy</p>
                <img
                    class="image"
                    alt="coral logo"
                    src="/src/assets/coral.png"
                />
            </div>
            <div
                on:click={selectProject}
                id="fitness_friend"
                class="project_card"
            >
                <p>MyFitnessFriend</p>
                <img
                    class="image"
                    alt="fitness logo"
                    src="/src/assets/fitness.png"
                />
            </div>
        </div>
    {/if}
</main>

<style>
    #project_wrapper {
        display: flex;
    }
    #expanded_projects {
        display: flex;
        flex-direction: row;
        align-items: center;
        align-content: center;
        justify-content: center;
        margin: 1rem;
    }
    .project_card {
        background-color: aliceblue;
        border-radius: 5%;
        text-align: center;
        margin: 0 0.25rem 0.5rem 0.25rem;
        padding: 1rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-evenly;
    }
    .project_card:hover {
        transition: ease-in;
        transition-duration: 100ms;
        cursor: pointer;
        box-shadow: rgb(48, 60, 68) 0px 20px 30px -10px;
        transform: translateY(-0.25rem);
    }
    p {
        margin: 0;
    }
    /* Small Screens*/
    @media only screen and (max-width: 768px) {
        #project_wrapper {
            max-width: 80vw;
            width: fit-content;
            flex-direction: row;
            flex-wrap: wrap;
            justify-content: space-evenly;
        }
        .project_card {
            width: 40vw;
            height: 15vh;
        }
        .image {
            max-width: 80%;
            height: 80%;
        }
    }
    /* Big Screens */
    @media only screen and (min-width: 768px) {
        #project_wrapper {
            max-width: 50vw;
            max-height: 40vw;
            flex-direction: row;
            justify-content: space-evenly;
            flex-wrap: wrap;
            align-content: center;
        }
        .project_card {
            width: 12rem;
            height: 12rem;
        }
        .image {
            max-width: 80%;
            max-height: 80%;
        }
    }
</style>
