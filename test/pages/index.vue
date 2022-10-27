<template>
  <section>
    <!-- Page style -->

    <div class="header">
      <h2>Welcome to Australian Prime Election Library</h2>
      <div class="navigation">
        <NuxtLink to="/candidate">See candidates</NuxtLink>
        <NuxtLink to="/">See elections</NuxtLink>
        <NuxtLink to="/about">About this website</NuxtLink>
      </div>
    </div>
    <!-- header -->
      <Election />

      <footer class="distributed">

          <div class="left">
              <h3>Created by Jacob</h3>
          </div>

          <div class="middle">
              <p>@University of Canberra</p>
          </div>
        </footer>
      <!-- Footer -->

  </section>
</template>


<script>
import Election from '~/components/Election.vue';
 export default {
    data() {
        return {
            speeches: [],
        };
    },
    async fetch() {
        // This is how to fetch the API
        const apiData = await fetch("https://electionspeeches.moadoph.gov.au/api/speeches.json")
            .then((response) => response.json());
        console.log(apiData);
        this.speeches = apiData;
    },
    components: { Election }
}
</script>

<style>

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Poppins", sans-serif;
}

section {
    position: relative;
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    background-color: rgb(16, 75, 236);
}

/* Header CSS */

.header {
    position: relative;
    top: 0;
    width: 100%;
    padding: 40px 100px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: rgb(236, 185, 44);
}

.header h2 {
    position: relative;
    color: #000;
    font-size: 30px;
    text-decoration: none;
    text-transform: uppercase;
    font-weight: 800;
    letter-spacing: 1px;
}

.header .navigation {
    color:#000;
    background: #fff;
    font-weight: 500;
    letter-spacing: 1px;
    padding: 4px 40px;
    border-radius: 15px;
}

a {
  text-decoration: none;
}

.header .navigation a {
  color: rgb(8, 113, 199);
}

.header .navigation a:hover {
  color: rgb(28, 241, 213);
}


.header .navigation a:not(:last-child) {
    margin-right: 30px;
    text-decoration-line: none
}

.header .navigation a:hover {
    background: #fff;
}

/* Footer CSS */

footer {
    text-align: center;
    padding-top: 100px;
    font-size: 35px;
    bottom: 0;
}

.distributed {
    background-color: #2d2a30;
    box-sizing: border-box;
    width: 100%;
    text-align: left;
    font: bold 16px sans-serif;
    padding: 50px 50px 60px 50px;
    margin-top: 80px;
}

.distributed .left, .distributed .middle {
    display: inline-block;
    vertical-align: top;
}

/* Left */

.distributed .left {
    width: 30%;
}

.distributed h3 {
    color: #ffffff;
    font: normal 36px 'Cookie', cursive;
    margin: 0;
}

/* Middle */

.distributed .middle {
    width: 35%;
}

.distributed .middle p {
    display: inline-block;
    color: #ffffff;
    vertical-align: middle;
    margin: 0;
}

/* Reponsive */
@media (min-width:640px) and (max-width: 1024px) {

.header h2 {
  display: none;
}

.header .navigation{
  padding: 4px 4em;
  text-align: center;
}
}

@media (max-width: 639px) {

.header h2 {
  display: none;
}

.header .navigation{
  text-align: center;
  font-size: 0.3em;
}

}

</style>