<header id="main_header">
    <div id="header_content">
        <p id="welcome">Hello!</p>
        <div id="about_me">
            <p class="blurb">
                My name is Colby Wang, I'm a Computer Science student at the
                University of Central Florida and I'm currently looking to gain
                more experience in Full-Stack development.
            </p>
            <p class="blurb">
                I enjoy working with Java and Typescript, and I'm currently
                learning Rust.
            </p>
        </div>
    </div>
</header>

<style>
    #main_header {
        color: aliceblue;
    }
    #welcome {
        font-size: 3rem;
        margin: 0;
    }
    #about_me {
        font-size: 1.1rem;
        margin: 0;
    }
    @media only screen and (max-width: 768px) {
        #main_header {
            max-width: 90vw;
            min-width: 90vw;
        }
        #header_content {
            text-align: center;
        }
    }
    @media only screen and (min-width: 768px) {
        #main_header {
            max-width: 50vw;
            max-height: 40vh;
        }
    }
</style>
