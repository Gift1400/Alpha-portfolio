<template>

  <header>
    <h2>{{ logo }}</h2>
  </header>

  <div class="loading-screen" v-if="loading">
    <h1 v-for="(letter, index) in letters" :key="index" :style="{ animationDelay: index * 0.15 + 's' }">
      {{ letter }}
    </h1>
  </div>


  <section class="main-content" v-if="showMain">
    <article class="content-panel">
      <img :src="profileImage" alt="profile-image" id="profile-image" />

      <article class="summary">
        <h2>Junior Software Developer | Web Designer</h2>
      </article>

      <div class="buttons">
        <button id="download-resume"><img :src="downloadLogo" alt="download-icon" id="download" />Resume</button>
        <button id="projects"><img :src="projectIcon" alt="stack image" id="project-icon" />Projects</button>
      </div>
    </article>

    <article class="info-panel">
      <article id="mac-panel">
        <div id="head">
          <img v-for="(icon, index) in icons" :key="index" :src="icon" id="dot">
        </div>
        <div id="text-content">

        </div>
      </article>

    </article>
  </section>

</template>

<script>
export default {
  data() {
    return {
      profileImage: require('@/assets/profile-image.png'),
      scrollIcon: require('@/assets/scroll-icon.png'),
      logo: "</Gift>",
      downloadLogo: require('@/assets/download-icon.png'),
      projectsIcon: require('@/assets/projects-icon.png'),

      letters: [
        'G',
        'I',
        'F',
        'T'
      ],
      loading: true,
      showMain: false,

      icons: [
        require('@/assets/red-dot.png'),
        require('@/assets/yellow-dot.png'),
        require('@/assets/green-dot.png')
      ]

    };
  },

  mounted() {
    const letterDelay = 0.15;
    const letterDuration = 1;
    const totalTime = (this.letters.length * letterDelay + letterDuration) * 1000;

    setTimeout(() => {
      this.loading = false;
      this.showMain = true;
    }, totalTime);
  }


};
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
  background-color: black;
  min-height: 100%;
  width: 100%;
}

header {
  position: fixed;
  display: flex;
  flex-direction: row;
  top: 0;
  left: 0;
  width: 100%;
  height: 10vh;
  background: rgba(168, 168, 168, 0.22);
  backdrop-filter: blur(15px);
  z-index: 90;

}

body {
  position: Relative;
  padding-top: 10vh;
  width: 100%;
}

header h2 {
  position: absolute;
  font-size: 25px;
  font-weight: 500;
  color: white;
  text-align: center;
  left: 50px;

}

/*Loading screen*/

.loading-screen {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  font-size: 50px;
  color: white;
  z-index: 10;

}

.loading-screen h1 {
  font-family: "Irish Grover", system-ui;
  font-weight: 400;
  display: inline-block;
  animation: growShrink 0.6s ease-in-out;
  animation-fill-mode: both;
}


/*Main content*/

.main-content {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex: 2;
  width: 80%;
  height: 70vh;
  border: 1px solid rgb(255, 255, 255);
  border-radius: 30px;
  z-index: 5;
  background-color: rgba(183, 183, 183, 0.2);
  backdrop-filter: blur(15px);

}

.content-panel {
  position: relative;
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 100%;
  align-items: center;
  justify-content: center;
  flex: 1;
}

#profile-image {
  position: relative;
  display: flex;
  bottom: 40px;
  width: 150px;
  height: 150px;
  border-radius: 100px;

}

.summary {
  position: relative;
  display: flex;
  bottom: 20px;
  width: 70%;
  height: 200px;
  justify-content: center;
  border: 1px solid rgb(255, 255, 255);
  border-radius: 20px;
  backdrop-filter: blur(15px);
}

.summary h2 {
  color: white;
  font-weight: lighter;
  font-size: 20px;

}

.buttons {
  position: relative;
  display: flex;
  top: 10px;
  gap: 50px;

}

#download-resume {
  display: flex;
  width: 200px;
  height: 50px;
  border: .5px solid white;
  color: white;
  gap: 20px;
  border-radius: 30px;
  align-items: center;
  justify-content: center;
  background-color: rgba(0, 0, 0, 0.2);
  font-size: 20px;
}

#download {
  width: 30px;
  height: 30px;

}

#projects {
  display: flex;
  gap: 20px;
  align-items: center;
  width: 200px;
  height: 50px;
  border: .5px solid white;
  border-radius: 30px;
  background-color: rgba(0, 0, 0, 0.2);
  font-size: 20px;
}

#projects-icon {
  width: 25px;
  height: 25px;
}



/*Information Panel*/

.info-panel {
  position: relative;
  display: flex;
  flex: 1;
  border: .5px solid white;
  align-items: center;
  justify-content: center;
}

#mac-panel {
  position: relative;
  display: flex;
  width: 60%;
  height: 80%;
  border: .5px solid white;
  border-radius: 20px;
  background-color: rgba(0, 0, 0, 0.65);
  backdrop-filter: blur(15px);
}

#head {
  position: relative;
  display: flex;
  width: 100%;
  height: 50px;
  align-items: center;
  border-top-right-radius: 20px;
  border-top-left-radius: 20px;
  background-color: black;

}

#dot {
  position: relative;
  width: 15px;
  height: 15px;
  left: 10px;
  padding-left: 8px;
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

/* Key Frames for animation*/

@keyframes bounce {

  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(10px);
  }
}

@keyframes growShrink {

  0% {
    transform: scale(1);
    opacity: 1;
  }

  50% {
    transform: scale(1.8);
  }

  100% {
    transform: scale(1);
    opacity: 1;
  }

}
</style>
