<script>
    import { createEventDispatcher } from "svelte";
import VaSt from "./experiences/VaST.svelte";

    export let experience;

    const dispatch = createEventDispatcher();

    function selectExperience(event) {
        const selectedExperience = event.target.id 
            ? event.target.id
            : event.target.parentElement.id;
        dispatch("message", {
            experience: selectedExperience
        })
    }


</script>


<div id="experience_wrapper">
    {#if experience}
        {#if experience === "vast"}
            <VaSt/>
        {/if}
    {/if}
    {#if !experience}
    <div on:click={selectExperience} class="experience_container" id="vast">
        <div class="experience_header">Virginia Systems and Technology</div>
    </div>
    {/if}
</div>


<style>
    .experience_container {
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
    .experience_header {
        font-size: larger;
    }
    .experience_container:hover {
        transition: ease-in;
        transition-duration: 100ms;
        cursor: pointer;
        box-shadow: rgb(48, 60, 68) 0px 20px 30px -10px;
        transform: translateY(-0.25rem);
    }
     /* Small Screens*/
     @media only screen and (max-width: 768px) {
        #experience_wrapper {
            max-width: 80vw;
            width: fit-content;
            flex-direction: row;
            flex-wrap: wrap;
            justify-content: space-evenly;
        }
        .experience_container {
            width: 40vw;
            height: 15vh;
        }
    }
    /* Big Screens */
    @media only screen and (min-width: 768px) {
        #experience_wrapper {
            max-width: 50vw;
            max-height: 40vw;
            flex-direction: row;
            justify-content: space-evenly;
            flex-wrap: wrap;
            align-content: center;
        }
        .experience_container {
            width: 12rem;
            height: 12rem;
        }
    }

</style>