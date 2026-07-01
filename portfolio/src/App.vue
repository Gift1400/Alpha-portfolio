<template>

  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <link href="https://fonts.googleapis.com/css2?family=Alfa+Slab+One&family=Orbitron&display=swap" rel="stylesheet">

  <header>
    <h2>{{ logo }}</h2>
  </header>

  <body>

    <section class="portfolio">

      <div class="scroll-view">
        <h2 class="scroll">Scroll down</h2>
        <img :src="scrollIcon" alt="scrolling arrows" class="scroll-icon">
      </div>

      <div class="bottomBtns">
        <a :href="myResume" download="Sinethemba-Mkhoma(cv).pdf">
          <Button class="resume">Resume</Button>
        </a>

        <Button class="contactInfo">Contact Info</Button>
      </div>

    </section>



  </body>

</template>

<script>
export default {
  data() {
    return {
      profileImage: require('@/assets/profile2.png'),
      scrollIcon: require('@/assets/scroll-icon.png'),
      photos: [
        require('@/assets/photo1.png'),
        require('@/assets/photo2.jpg'),
        require('@/assets/photo3.jpg'),
        require('@/assets/photo4.jpg'),
        require('@/assets/photo5.jpg'),
        require('@/assets/photo6.jpg'),
      ],
      logo: "</Gift>",

    };
  },


};
</script>

<style>
html {
  background-color: rgb(0, 0, 0);
  width: 100%;
  margin: 0;
  padding: 0;
}

header {
  position: fixed;
  display: flex;
  flex-direction: row;
  top: 0;
  left: 0;
  width: 100vw;
  height: 15vh;
  background: rgba(222, 222, 222, 0.284);
  backdrop-filter: blur(10px);
  z-index: 90;

}

header h2 {
  position: absolute;
  font-size: 25px;
  font-weight: 500;
  color: white;
  text-align: center;
  left: 30px;

}




.scroll-view {
  position: absolute;
  top: 40px;
  display: flex;
  flex-direction: column;
  align-items: center;
  top: 80%;
  color: white;
  justify-self: center;
  justify-items: center;
  height: 80px;
}

.scroll {
  font-size: medium;
  font: italic;
  margin-top: 40px;
}

.scroll-icon {
  width: 30px;
  height: auto;
  animation: bounce 1.5s infinite;
}

@keyframes bounce {

  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(10px);
  }
}
</style>
