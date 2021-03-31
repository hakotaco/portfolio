<template>
  <div class="timelinechart-container">
    <div v-for="(tl, i) in timelineArr" :key="i" class="timeline-object animate__animated animate__fadeInUp animate__delay-1s">
      <span class="animate__animated animate__fadeInUp animate__delay-1s"></span>
      <div>
        <span>{{tl.line1}}</span>
        <span>{{tl.line2}}</span>
        <span>{{tl.line3}}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TimelineChart',
  props: {
    timelineArr: {
      type: Array,
      required: true
    }
  }
}
</script>

<style>
  .timelinechart-container {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    flex-direction: column;
    overflow-y: auto;
    padding-left: 5px;
    margin-top: 20px;
  }

  .timeline-object {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding-bottom: 40px;
    border-left: 2px solid #000000;
    padding-left: 20px;
  }

  .timeline-object:last-child {
    padding-bottom: 10px;
  }

  .timeline-object > span {
    background-color: #000;
    width: 10px;
    min-width: 10px;
    height: 10px;
    border-radius: 5px;
    margin-left: -26px;
    z-index: 100;
  }

  .timeline-object > div {
    display: flex;
    justify-content: flex-start;
    align-items: flex-start;
    flex-direction: column;
    padding-left: 10px;
  }

  .timeline-object > div > span {
    font-family: Quicksand;
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    color: #000000;
  }

</style>