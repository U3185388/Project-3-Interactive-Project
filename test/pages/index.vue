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
</style>