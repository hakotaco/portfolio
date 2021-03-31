<template>
  <div class="parent">
    <NavBar />
    <div class="center-circle"></div>
    <div class="container">
      <h1 class="animate__animated animate__fadeInUp">Contact Me</h1>
      <p class="animate__animated animate__fadeInUp animate__delay-1s">
        Be it some doubt, freelance work, a job offer &#128584;, or anything else! Please don't hesitate to reach out to me through the following means.
      </p>
      <div class="socials-container">
        <a href="mailto:ashutosh.kaushik1999@gmail.com"><img src="../assets/mail.svg" alt="instagram"></a>
        <a href="https://www.linkedin.com/in/ashdarkfold/"><img src="../assets/linkedin.svg" alt="instagram"></a>
        <a href="https://twitter.com/Kaushikxx_"><img src="../assets/twitter.svg" alt="instagram"></a>
        <a href="https://www.instagram.com/ashdarkfold"><img src="../assets/instagram.svg" alt="instagram"></a>
      </div>
    </div>
    <div class="ill-container animate__animated animate__fadeInRight">
      <img src="../assets/contact.svg" />
    </div>
  </div>
</template>

<script>
import NavBar from '../components/NavBar'

export default {
  name: "Contact",
  components: {
    NavBar
  },
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

  .socials-container {
    display: flex;
    width: 100%;
    justify-content: space-evenly;
    align-items: flex-start;
    margin-top: 20px;
  }

  .socials-container img {
    width: 30px;
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
      justify-content: unset;
      margin-top: 100px;
    }
  }
</style>