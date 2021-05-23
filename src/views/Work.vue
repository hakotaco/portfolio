<template>
  <div class="parent">
    <NavBar />
    <div class="center-circle"></div>
    <div class="container">
      <h1 class="animate__animated animate__fadeInUp">Work</h1>
      <p class="animate__animated animate__fadeInLeft">
        These are some of the projects i’ve worked on that are live right now.<br/>
        However, not everything I’ve worked on is up for the world to see, unfortunately. You can check out my <a href="https://www.github.com/AshDarkfold" target="_blank">github</a> to see all the projects i’ve contributed to!
      </p>
      <div class="work-container">
        <a class="animate__animated animate__fadeInLeft" v-for="(w, i) in work" :key="i" target="_blank" :href="w.url">
          <div class="work-card">
            <img :src="w.img" />
            <span>{{w.name}}</span>
          </div>
        </a>
      </div>

    </div>
    <div class="ill-container animate__animated animate__fadeInRight">
      <img src="../assets/work.svg" />
    </div>
  </div>
</template>

<script>
import NavBar from '../components/NavBar'
import work from '../data/work'

export default {
  name: 'Work',
  components: {
    NavBar
  },
  data: function() {
    return {work}
  }
}
</script>

<style scoped>
  .parent {
    width: 100vw;
    position: relative;
    height: 100vh;
  }

  .center-circle {
    position: absolute;
    left: 0;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 100vw;
    height: 0;
    padding-top: 100%;
    background-color: #FFEE51;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    transition: all 0.6s ease;
    cursor: pointer;
  }

  .container {
    position: absolute;
    left: 0;
    top: 0;
    width: 40%;
    text-align: left;
    padding: 0 40px;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    flex-direction: column;
    box-sizing: border-box;
    overflow: auto;
  }

  .ill-container {
    position: absolute;
    right: 0;
    top: 0;
    width: 40%;
    text-align: left;
    padding: 0 40px;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .ill-container > img {
    width: 100%;
    height: auto;
  }

  .work-container {
    display: flex;
    height: fit-content;
    max-height: 50%;
    overflow-x: auto;
    white-space: nowrap;
    padding: 10px;
    position: relative;
    width: 100%;
    box-sizing: border-box;
  }

  .work-container > a {
    width: 400px;
    min-width: 100%;
    margin-right: 20px;
    height: fit-content;
    box-sizing: border-box;
  }

  .work-card {
    width: 100%;
    display: flex;
    flex-direction: column;
    transition: all 0.3s ease;
    position: relative;
    border-radius: 10px;
    max-width: 100%;
    background-color: #fff;
    padding: 10px;
    box-sizing: border-box;
    box-shadow: 0px 5px 10px rgba(0,0,0,0.2);
  }

  .work-card:hover {
    box-shadow: 10px 10px 10px rgba(0,0,0,0.3);
  }

  .work-card img {
    width: 100%;
    height: 225px;
    object-fit: cover;
    object-position: left;
    border-radius: 10px;
  }

  .work-card > span {
    font-size: 24px;
    background: rgba(0,0,0,0);
    color: rgba(0,0,0,1);
    margin: 0;
    padding: 5px;
    box-sizing: border-box;
    text-decoration: none;
  }

  @media (max-width: 991px) {
      .ill-container {
        display: none;
      }

      .center-circle {
        opacity: 0.3;
      }

      .container {
        width: 100%;
        justify-content: unset;
        margin-top: 100px;
      }
  }
</style>