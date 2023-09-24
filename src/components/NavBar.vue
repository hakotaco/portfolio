<template>
  <div class="nav-container">
    <router-link to="/"
      ><img src="../assets/logo.svg" alt="Ashutosh kaushik's logo"
    /></router-link>
    <div class="nav">
      <ul>
        <li v-on:click="handleMenu" id="about" class="menu-item">About Me</li>
        <li v-on:click="handleMenu" id="timeline" class="menu-item">
          Timeline
        </li>
        <li v-on:click="handleMenu" id="work" class="menu-item">Work</li>
        <li v-on:click="handleMenu" id="contact" class="menu-item">
          Contact Me
        </li>
        <li id="resume" class="menu-item">
          <a
            href="https://drive.google.com/file/d/1Z-0kH4kolM6hNLJr-Doma0Us-U0ejXpR/view?usp=sharing"
            target="_blank"
            style="text-decoration: none; color: #000"
            >Résumé</a
          >
        </li>
      </ul>
    </div>
    <div class="mobile-nav">
      <ul>
        <li tabindex="0" class="has-dropdown">
          <button class="drpdwn-button">
            <img src="../assets/menu.svg" />
          </button>
          <ul class="dropdown" id="dropdown">
            <li class="menu-item">
              <router-link to="/about">About</router-link>
            </li>
            <li class="menu-item">
              <router-link to="/timeline">Timeline</router-link>
            </li>
            <li class="menu-item">
              <router-link to="/work">Work</router-link>
            </li>
            <li class="menu-item">
              <router-link to="/contact">Contact Me</router-link>
            </li>
            <li id="resume" class="menu-item">
              <a
                href="https://drive.google.com/file/d/1gKDGKCOZYT4HOfAyhwDO_OAsOccDhwsQ/view?usp=sharing"
                target="_blank"
              >
                Résumé
              </a>
            </li>
          </ul>
        </li>
      </ul>

      <div></div>
    </div>
    <div class="highlight" id="highlight" />
  </div>
</template>

<script>
export default {
  name: "NavBar",
  methods: {
    handleMenu: function (e) {
      let highlight = document.getElementById("highlight");
      highlight.style.left = e.target.offsetLeft.toString() + "px";
      highlight.style.top = e.target.offsetTop.toString() + "px";
      highlight.style.width = e.target.offsetWidth.toString() + "px";
      setTimeout(() => {
        this.$router.push(e.target.id);
      }, 400);
    },
    initHighlight: function () {
      console.log("hep");
      let currRoute = this.$router.history.current.path;
      if (currRoute !== "/" && window.innerWidth > 991) {
        let toSelect = document.getElementById(currRoute.substring(1));
        let highlight = document.getElementById("highlight");
        highlight.style.left = toSelect.offsetLeft.toString() + "px";
        highlight.style.top = toSelect.offsetTop.toString() + "px";
        highlight.style.width = toSelect.offsetWidth.toString() + "px";
      } else {
        let highlightDel = document.getElementById("highlight");
        if (highlightDel) {
          highlightDel.style.width = "0";
        }
      }
    },
  },
  mounted: function () {
    this.initHighlight();
    window.addEventListener("resize", () => {
      this.initHighlight();
    });
  },
};
</script>

<style>
.nav-container {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 80px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 5;
  padding: 10px 40px;
  box-sizing: border-box;
}

.nav-container > a > img {
  width: 70px;
  height: auto;
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
  background-color: #ffee51;
  display: block;
  position: fixed;
  height: 20px;
  opacity: 0.3;
  z-index: 0;
  transition: all 0.4s ease;
}

.nav > ul > li:hover {
  text-shadow: 0px 0px 3px rgba(0, 0, 0, 0.2);
}

.mobile-nav {
  display: none;
}

.mobile-nav > ul {
  list-style: none;
}

.mobile-nav button {
  background-color: rgba(0, 0, 0, 0);
  border: none;
  outline: 0 !important;
  cursor: pointer;
  transition: all 0.3s ease;
}

.mobile-nav button:active {
  filter: drop-shadow(0px 0px 5px rgba(0, 0, 0, 0.3));
}

.dropdown {
  position: fixed;
  z-index: 1000;
  top: 20px;
  right: 40px;
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: #ffee51;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 5px !important;
  box-sizing: border-box;
  opacity: 0;
  transition: all 0.2s ease;
  pointer-events: none;
}

.dropdown > li {
  width: 100%;
  color: #000;
  list-style: none;
  cursor: pointer;
  margin-bottom: 5px;
}

.has-dropdown:focus-within .dropdown {
  opacity: 1;
  pointer-events: auto !important;
}

.menu-item > a {
  text-decoration: none;
  color: #000 !important;
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
