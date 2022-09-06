<script>
  import Experience from "./components/Experience.svelte";
  import Header from "./components/Header.svelte";
  import Navigator from "./components/Navigator.svelte";
  import Projects from "./components/Projects.svelte";

  let currentPage = "about";
  let currentProject = undefined;

  //Handles click events that are sent by the Navigator component
  //Sets the current project to undefined since we clicked on the nav
  //Sets the current page to whatever was passed in through the dispatch event
  function handleClick(event) {
    const target = event.detail.target;
    currentProject = undefined;
    switch (target) {
      case "about_button":
        currentPage = "about";
        break;
      case "project_button":
        currentPage = "projects";
        break;
      case "experience":
        currentPage = "experience";
        break;
    }
  }

  //Sets the current project modal 
  function setProject(event) {
    if (verifyProject(event.detail.project)) {
      currentProject = event.detail.project;
    }
  }

  //Verifies that a project was actually clicked on
  function verifyProject(project) {
    switch (project) {
      case "java_bot":
        return true;
      case "reef_buddy":
        return true;
      case "fitness_friend":
        return true;
      default:
        return false;
    }
  }

  //Handles clicking outside of the project modal and closes the modal
  function handleOutsideClick(event) {
    if (event.target.id == "main_container") {
      currentProject = undefined;
    }
  }
</script>

<main id="content_wrapper">
  <div id="main_container" on:click={handleOutsideClick}>
    {#if currentPage === "about"}
      <Header />
    {:else if currentPage === "projects"}
      <Projects project={currentProject} on:message={setProject} />
    {:else if currentPage === "experience"}
      <Experience />
    {/if}
    <Navigator on:message={handleClick} />
  </div>
</main>

<style>
  #content_wrapper {
    background-image: linear-gradient(rgb(63, 63, 63), rgb(53, 53, 53));
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  #main_container {
    display: flex;
    height: 100vh;
  }
  @media only screen and (max-width: 768px) {
    #main_container {
      flex-direction: column-reverse;
      justify-content: flex-end;
      align-items: center;
      width: 95vw;
    }
  }

  @media only screen and (min-width: 768px) {
    #content_wrapper {
      justify-content: center;
      align-content: center;
    }
    #main_container {
      flex-direction: row;
      justify-content: space-evenly;
      align-content: center;
      align-items: center;
      width: 80vw;
    }
  }
</style>
