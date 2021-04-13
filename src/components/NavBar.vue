<template>
  <div class="nav-container">
    <div class="nav">
      <ul>
        <li v-on:click="handleMenu" id="about" class="menu-item">About Me</li>
        <li v-on:click="handleMenu" id="timeline" class="menu-item">Timeline</li>
        <li v-on:click="handleMenu" id="work" class="menu-item">Work</li>
        <li v-on:click="handleMenu" id="contact" class="menu-item">Contact Me</li>
        <li id="resume" class="menu-item"><a href="https://drive.google.com/file/d/1gy30JjQcoE9CLXIQeuCNTT65xlcYVATN/view?usp=sharing" target="_blank" style="text-decoration: none; color: #000;">Résumé</a></li>
      </ul>
    </div>
    <div class="mobile-nav">
      <button v-on:click="makeDropdown" class="drpdwn-button">
        <img src="../assets/menu.svg" />
      </button>
      <div class="dropdown animate__animated" id="dropdown">
        <ul>
          <li v-on:click="handleMenu2" id="about" class="menu-item">About Me</li>
          <li v-on:click="handleMenu2" id="timeline" class="menu-item">Timeline</li>
          <li v-on:click="handleMenu2" id="work" class="menu-item">Work</li>
          <li v-on:click="handleMenu2" id="contact" class="menu-item">Contact Me</li>
          <li id="resume" class="menu-item"><a href="https://drive.google.com/file/d/1gy30JjQcoE9CLXIQeuCNTT65xlcYVATN/view?usp=sharing" target="_blank" style="text-decoration: none; color: #000;">Résumé</a></li>
        </ul>
      </div>
    </div>
    <div class="highlight" id="highlight" />
  </div>
</template>

<script>
  export default {
    name: "NavBar",
    methods: {
      handleMenu: function(e) {
        let highlight = document.getElementById('highlight')
        highlight.style.left = e.target.offsetLeft.toString() + "px"
        highlight.style.top = e.target.offsetTop.toString() + "px"
        highlight.style.width = e.target.offsetWidth.toString() + "px"
        setTimeout(()=>{
          this.$router.push(e.target.id)
        }, 400)
      },
      initHighlight: function() {
        let currRoute = this.$router.history.current.path
        if(currRoute !== "/" && window.innerWidth > 991) {

          let toSelect = document.getElementById(currRoute.substring(1))
          let highlight = document.getElementById('highlight')
          highlight.style.left = toSelect.offsetLeft.toString() + "px"
          highlight.style.top = toSelect.offsetTop.toString() + "px"
          highlight.style.width = toSelect.offsetWidth.toString() + "px"
        }
      },
      makeDropdown: function(e) {
        let rightDist = e.clientX
        let dropdown = document.getElementById('dropdown')
        if(dropdown.style.display === 'flex'){
          dropdown.classList.remove('animate__bounceIn')
          dropdown.style.display = 'none'
        }else{
          dropdown.style.opacity = '0'
          dropdown.style.display = 'flex'
          dropdown.style.left = (rightDist - 180)+'px'
          dropdown.classList.add('animate__bounceIn')

        }
      },
      handleMenu2: function(e) {
        this.$router.push(e.target.id)
      }
    },
    mounted: function() {
      this.initHighlight()
      window.addEventListener('resize', () => {
        this.initHighlight()
      })
    }
  }
</script>

<style>
  .nav-container {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 80px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    z-index: 5;
    padding: 10px 40px;
    box-sizing: border-box;
  }

  .nav {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .nav > ul {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .nav > ul > .menu-item {
    margin: 0px 15px;
    color: #000;
    padding-bottom: 3px;
    list-style: none;
    cursor: pointer;
    transition: all 0.3s ease;
    z-index: 1;
  }

  .highlight {
    background-color: #FFEE51;
    display: block;
    position: fixed;
    height: 20px;
    opacity: 0.3;
    z-index: 0;
    transition: all 0.4s ease;
  }

  .nav > ul > li:hover{
    text-shadow: 0px 0px 5px rgba(0,0,0,0.3);
  }

  .mobile-nav {
    display: none;
  }

  .mobile-nav button {
    background-color: rgba(0,0,0,0);
    border: none;
    outline: 0 !important;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .mobile-nav button:active {
    filter: drop-shadow(0px 0px 5px rgba(0,0,0,0.3));
  }

  .dropdown {
    position: fixed;
    z-index: 1000;
    display: none;
    top: 20px;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    background-color: #FFEE51;
    justify-content: center;
    align-items: center;
  }

  .dropdown > ul {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    width: 100%;
    padding: 5px !important;
    margin: 0;
    box-sizing: border-box;
  }

  .dropdown > ul > li {
    width: 100%;
    color: #000;
    list-style: none;
    cursor: pointer;
    margin-bottom: 5px;
  }

  @media (max-width: 991px) {
    .nav {
      display: none;
    }

    .mobile-nav {
      display: block;
    }
  }
</style>