<template>
  <div id="image-header">
      <header class="row">
        <div class="col-md-12">
            <div class="jumbotron jumbotron-fluid">
                <div class="top-menu">
                    <ul class="nav">
                        <li class="nav-item">
                            <nuxt-link to="/" class='nuxt-link'> Home </nuxt-link>
                        </li>
                        <li class="nav-item">
                            <nuxt-link to="/accordion-questions" class='nuxt-link'> About Us </nuxt-link>
                        </li>
                        <li class="nav-item">
                            <nuxt-link to="/Grid" class='nuxt-link'> Instructors </nuxt-link>
                        </li>
                        <li class="nav-item">
                            <nuxt-link to="/Images" class='nuxt-link'> Academics </nuxt-link>
                        </li>
                        <li class="nav-item">
                            <nuxt-link to="/movies" class='nuxt-link'> Movies! </nuxt-link>
                        </li>
                    </ul>
                </div>
                <div class="header-container">
                    <h1 class="display-1">Greywood School</h1>
                    <p class="lead">Personalized Education</p>
                </div>
            </div>
        </div>
       </header>
  </div>
</template>

<script>
export default {
  name: 'imageHeader'
}
</script>

<style>
.jumbotron {
    background-image: url("../static/img/blossoms.jpg");
    background-size: cover;
    display: flex;
    flex-direction: column;
    text-align: center;
}

.header-container {
    margin: 1em;   
}

.nuxt-link {
  padding: 1em;
}
.top-menu {
    display: flex;
    flex-direction: row;
    justify-content: center;
}
</style>