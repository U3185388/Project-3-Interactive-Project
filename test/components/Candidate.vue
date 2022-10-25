<template>

  <div class="container">
          <h5 v-if="$fetchState.pending">Just a monent...</h5>
          <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
    <!-- This is the error feedback -->

      <ul v-for="candidate in candidates" :key="candidate.id">
          <li><span></span>
              <div class="title">
                <h3>{{  candidate.name  }}</h3>
              </div>
              
                <div class="info">
                <p class="detail">{{ candidate.bio }}</p>
              </div>

              <div class="link"><NuxtLink :to="'/speeches/' + candidate.id">Click to see more information</NuxtLink></div>
          </li>
      </ul>
    </div>

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