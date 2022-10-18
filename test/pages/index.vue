<template>
    <section id="home">
    <!-- Page style -->

    <div class="header">
      <NuxtLink to="/candidate">See candidates</NuxtLink>
    </div>
    <!-- Candidate swticher -->

    <div class="container">
      <h5 v-if="$fetchState.pending">Just a monent...</h5>
      <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
      <!-- This is the error feedback -->

      <div v-for="speech in speeches" :key="speech.id">
        <NuxtLink :to="'/speeches/' + speech.id">{{ speech.title }}
         </NuxtLink>
        </div>
    </div>
    <!-- This is the container for election; From the first to end -->

</section>
</template>


<script>
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
}
</script>
