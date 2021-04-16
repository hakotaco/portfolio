<template>
  <div class="parent">
   <NavBar />
    <div class="center-circle"></div>
    <div class="container">
      <h1 class="animate__animated animate__fadeInUp">Timeline</h1>
      <div class="timeline">
        <timeline-chart v-bind:timelineArr="mainData" />
      </div>
    </div>
    <div class="ill-container animate__animated animate__fadeInRight">
      <img src="../assets/timeline.svg" />
    </div>
  </div>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import TimelineChart from '../components/TimelineChart.vue'
import timelineData from '../data/timeline'

export default {
  name: 'Timeline',
  components: {
    NavBar,
    TimelineChart
  },
  data: function() {
    return {
      mainData: timelineData
    }
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

  .timeline {
    width: 100%;
    height: 60%;
    max-height: 60%;
    overflow-y: auto;
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
        justify-content: unset;
        margin-top: 100px;
        height: calc(100% - 100px);
      }

      .timeline {
        height: unset;
        max-height: unset;
        margin-bottom: 20px;
      }
  }
</style>