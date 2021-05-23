<template>
  <div class="parent">
   <NavBar />
    <div class="center-circle"></div>
    <div class="container">
      <main>
        <h1 class="animate__animated animate__fadeInUp">About me</h1>
        <p class="animate__animated animate__fadeInLeft">
          A passionate developer with a dream. A dream to provide the best user experience out there. I’ve been consistently developing software with various companies, organisations, startups and clients since December 2019.
          I’m proficient in JavaScript, both backend and frontend. Highly experienced in react and have a good hold of the fundamentals of Vue, Next JS and a bunch of commonly used libraries like bootstrap, ant-design etc.
        </p>
        <p class="animate__animated animate__fadeInLeft">
          I write efficient REST API’s using Node.JS and Golang and have a good amount of experience with relational (MySql, Postgresql) and non-relational (MongoDB) databases.
        </p>
        <p class="animate__animated animate__fadeInLeft">
          I’m a fan of paying attention to detail and understand how important it is. 
          I design websites and android apps as a hobby and although, haven’t ever designed one professionally, I have made a bunch of sample designs to test my skills.
        </p>
        <p class="animate__animated animate__fadeInLeft">
          (You can find projects using all of the above <br/>mentioned skills in the work section) 
        </p>
      </main> 
    </div>
    <div class="ill-container animate__animated animate__fadeInRight">
      <img src="../assets/about.svg" />
    </div>
  </div>
</template>

<script>
import NavBar from '../components/NavBar'

export default {
  name: 'About',
  components: {
    NavBar
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
    padding: 0 100px;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    flex-direction: column;
    box-sizing: border-box;
    overflow: auto;
  }

  main {
    width: 100%;
    height: 60%;
    max-width: 400px;
    max-height: 60%;
    overflow-y: auto;
    overflow-x: hidden;
    justify-content: center;
    align-items: flex-start;
    flex-direction: column;
    box-sizing: border-box;
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

  @media (max-width: 991px) {
      .ill-container {
        display: none;
      }

      .center-circle {
        opacity: 0.3;
      }

      .container {
        width: 100%;
        justify-content: flex-start;
        margin-top: 100px;
        padding: 0 40px;
        height: 130%;
      }

      main {
        height: 100%;
        margin-bottom: 20px;
      }
  }
</style>