<template>
    <section id="home">
    <!-- Page style -->

    <div class="header">
      <NuxtLink to="/">See election</NuxtLink>
    </div>
    <!-- Election swticher -->

    <div class="container">
      <h5 v-if="$fetchState.pending">Just a monent...</h5>
      <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
      <!-- This is the error feedback -->

      <div class="text">
      <div v-for="candidate in candidates" :key="candidate.id">
         <NuxtLink :to="'/speeches/' + candidate.id">
         {{  candidate.name  }}
         </NuxtLink></div>
        </div>
    </div>
    <!-- This is the container for two candidates in each election -->

</section>
</template>


<script>
 export default {
   data() {
    return {
      candidates: [],
    }
   },

   async fetch() {
    // This is how to fetch the API

    const apiData = await fetch('https://electionspeeches.moadoph.gov.au/api/candidates.json')
		.then((response) =>
			response.json()
		)
		console.log(apiData)

    this.candidates = apiData;

   }
  }
</script>