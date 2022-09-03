<script>
  import Header from "./components/Header.svelte";
  import Navigator from "./components/Navigator.svelte";
  import Projects from "./components/Projects.svelte";

  let current_page = "about";

  function handleClick(event) {
    const target = event.detail.target;
    switch (target) {
      case "about_button":
        current_page = "about";
        break;
      case "project_button":
        current_page = "projects";
        break;
    }
  }
</script>

<main id="content_wrapper">
  <div id="main_container">
    {#if current_page === "about"}
      <Header />
    {:else if current_page === "projects"}
      <Projects />
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
    }
  @media only screen and (max-width: 768px) {
    #main_container {
      flex-direction: column-reverse;
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
      width: 80vw;
    }
  }
</style>
