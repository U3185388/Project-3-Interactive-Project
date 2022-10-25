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

      <div class="footer">
            <div class="f-navigation">
                <h4>Created by Jacob</h4>
                <h5>University of Canberra</h5>
                <p>Back to Top</p>
            </div>
      </div>
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
  color: red;
}


.header .navigation a:not(:last-child) {
    margin-right: 30px;
    text-decoration-line: none
}

.header .navigation a:hover {
    background: #fff;
}

/* Footer CSS */

.footer {
    position: relative;
    top: 0;
    width: 100%;
    padding: 15px 150px;
    display: flex;
    align-items: center;
    background-color: rgb(236, 185, 44);
}

</style>