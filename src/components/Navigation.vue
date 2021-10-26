<template>
  <nav class="navbar navbar-expand-lg navbar-dark fixed-top" id="nav">
    <div class="container">
      <a class="navbar-brand" href="">
        YiChun
        <br>
        Developer
      </a>
      <!-- Mobile -->
      <button class="navbar-toggler text-white" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon" />
      </button>
      <div class="collapse navbar-collapse" id="navbarNav" v-on:click="scroll">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item mx-0 mx-lg-1">
            <a class="nav-link py-3 px-0 px-lg-3 rounded" href="#home">HOME</a>
          </li>
          <li class="nav-item mx-0 mx-lg-1">
            <a class="nav-link py-3 px-0 px-lg-3 rounded" href="#about">ABOUT</a>
          </li>
          <li class="nav-item mx-0 mx-lg-1">
            <a class="nav-link py-3 px-0 px-lg-3 rounded" href="#project">PROJECT</a>
          </li>
          <li class="nav-item mx-0 mx-lg-1">
            <a class="nav-link py-3 px-0 px-lg-3 rounded" href="#skill">SKILL</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navigation",

  methods: {
    scroll() {
      if (window.innerWidth < 992) {
        document.querySelector('button').click()
      }
    }
  }
}
</script>

<style lang="scss" scoped>
#nav {
  background-color: $light-blue;
  font-weight: 700;

  a {
    color: white;
  }

  button {
    background-color: $light-green;
  }

  .navbar-brand {
    font-size: 1.75em;
  }

  button[aria-expanded="false"] {
    box-shadow: none;
  }

  #navbarNav {
    a:hover {
      color: $light-green;
    }

    a[class="nav-link py-3 px-0 px-lg-3 rounded active"] {
      color: white;
      background-color: $light-green;
    }
  }
}

@media (max-width: 992px) {
  #nav {
    br {
      display: none;
    }

    #navbarNav {
      a {
        text-align: left;
      }

      a[class="nav-link py-3 px-0 px-lg-3 rounded active"] {
        color: $light-green;
        background-color: transparent;
      }
    }
  }
}
</style>