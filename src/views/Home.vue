<template>
  <div class="home">
    <div id="center-circle" class="center-circle animate__animated animate__bounceIn" v-on:click="handleClick">
      <div>
        <h1>Hey,<br/>I'm Ashutosh</h1>
        <h3>Software Developer<br/>with a knack for UX</h3>
        <span>Click here to learn more</span>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  methods: {
    handleClick: function () {
      let ccir = document.getElementById('center-circle')
      if(ccir.childNodes.length) {
        ccir.removeChild(ccir.childNodes[0])
        ccir.style.maxWidth = '2000px'
        ccir.style.width = '100vw'
        ccir.style.minWidth = '100vw'
        ccir.style.height = '100vw'
        ccir.style.animationFillMode = 'none'
        setTimeout(()=> {
          ccir.style.transform = 'translateX(-50%)'
        })
        if(window.innerWidth < 991){
          ccir.style.opacity = '0.3'
        }
        setTimeout(() => {
          this.$router.push('about')
        }, 600)
      }
      
    }
  }
}
</script>

<style scoped>
  .home {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .center-circle {
    position: relative;
    width: 600px;
    min-width: 600px;
    height: 600px;
    background-color: #FFEE51;
    border-radius: 50%;
    transition: all 0.6s ease;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .center-circle:hover {
    box-shadow: 0px 0px 20px rgba(0,0,0,0.1);
  }

  .center-circle h1 {
    font-style: normal;
    font-weight: 500;
    font-size: 56px;
    text-align: center;
    color: #000000;
    margin: 0;
    margin-bottom: 30px;
  }

  .center-circle h3 {
    font-style: normal;
    font-weight: normal;
    font-size: 28px;
    text-align: center;
    color: #000000;
    margin: 0;
    margin-bottom: 30px;
  }

  .center-circle span {
    font-style: normal;
    font-weight: 300;
    font-size: 15px;
    text-align: center;
    color: #000000;
  }


  @media (max-width: 410px) {
    .center-circle h1 {
      font-size: 40px;
    }
    .center-circle h3 {
      font-size: 20px;
    }
    .center-circle span {
      font-size: 12px;
    }
  }
</style>