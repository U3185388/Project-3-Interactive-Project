<template>

  <div class="container">

      <ul>
            <li><span></span>
                <div class="title">
                  <h3>Alfred Deakin</h3>
                </div>
                
                  <div class="info">
                  <p class="detail">Alfred Deakin was born 3 August, 1856 and died 7 October, 1919. Deakin was the Prime Minister of Australia on three separate occasions: 24 September, 1903 to 27 April, 1904; 5 July, 1905 to 13 November, 1903; and 2 June, 1909 to 29 April, 1910. He was Leader of the Protectionist Party 1901 to 1910 and of the Liberal/"Fusion" Party 1909 to 1910. Deakin represented the electorate of Ballarat, Victoria 1901 to 1913.</p>
                </div>

                <div class="link"><NuxtLink :to="'/speeches/' + 42">Click to see more information</NuxtLink></div>
              </li>
          </ul>

          <ul>
            <li><span></span>
                <div class="title">
                  <h3>Andrew Fisher</h3>
                </div>
                
                  <div class="info">
                  <p class="detail">Andrew Fisher was born 29 August 1862 and died 22 October, 1928. Fisher was the Prime Minister of Australia on three separate occasions: 13 November, 1908 to 2 June, 1909; 29 April, 1910 to 24 June, 1913; and 17 September, 1914 to 27 October, 1915. He was the Leader of the Australian Labor Party. Fisher represented the electorate of Wide Bay, Queensland 1901 to 1915.</p>
                </div>

                <div class="link"><NuxtLink :to="'/speeches/' + 65">Click to see more information</NuxtLink></div>
            </li>
          </ul>

          <ul>
            <li><span></span>
                <div class="title">
                  <h3>Andrew Peacock</h3>
                </div>
                
                  <div class="info">
                  <p class="detail">Andrew Peacock was born 13 February, 1939. Peacock was the Leader of the Liberal Party and Leader of the Opposition on two separate occasions: 11 March, 1983 to 5 September, 1985; and 9 May, 1989 to 3 April 1990. He represented electorate of Kooyong, Victoria 1966 to 1994.</p>
                </div>

                <div class="link"><NuxtLink :to="'/speeches/' + 57">Click to see more information</NuxtLink></div>
            </li>
        </ul>

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

              <div class="link"><NuxtLink :to="'/speeches/' + candidate.id">Click to see different information</NuxtLink></div>
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