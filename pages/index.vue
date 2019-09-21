<template>
  <div class="tbl-home">
    <section
      id="home"
      class="black"
    >
      <ul>
        <li>Fiabilité</li>
        <li>Savoir faire</li>
        <li>Responsable</li>
      </ul>
    </section>
    <section
      id="skills"
      class="white"
    >
      SKILLS
    </section>
    <section
      id="partners"
      class="black"
    >
      PARTNERS
    </section>
    <section
      id="contact"
      class="white"
    >
      CONTACT
    </section>
  </div>
</template>

<script>

</script>

<style>
  .tbl-home section {
    min-height: calc(100vh - 70px);
    display: flex;
  }

  .tbl-home section.black {
    background-color: rgb(32, 30, 30);
    color: white;
  }

  .tbl-home section.white {
    background-color: white;
    color: rgb(32, 30, 30);
  }

  #home {
    background-image: url("/unsplash.jpg");
    background-repeat: no-repeat;
    background-size: cover;

    position: relative;

    z-index: 1;
  }

  #home::after {
    content: "";

    position: absolute;

    z-index: -1;

    top: 0;
    left: 0;

    height: 100%;
    width: 100%;
    background: linear-gradient(.3turn, rgb(32, 30, 30) 40%, rgba(48, 45, 45, .2) 90%)
  }

  #home ul {
    list-style: none;
    align-self: center;
    margin: 0;
    padding-left: 15%;
    font-size: 4em;
  }

  #home ul li {
    margin: 7% 0;
    font-family: "WorkSans";
    text-shadow: 0 7px 5px black;

    animation: slideIn 1.8s ease forwards;

    transform: translateX(100vw);
  }

  #home ul li:nth-child(2) {
    animation-delay: .5s;
  }

  #home ul li:nth-child(3) {
    animation-delay: 1s;
  }

  @keyframes slideIn {
    0% {
      transform: translateX(100vw);
    }

    100% {
      transform: translateX(0vw);
    }
  }
</style>
