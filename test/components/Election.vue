<template>

    <div class="container">

      <ul>
            <li><span></span>
                <div class="title">
                  <h3>1901</h3>
                </div>
                
                  <div class="info">
                  <p class="detail">This election was start at 1901-03-29</p>
                </div>

                <div class="link"><NuxtLink :to="'/speeches/' + 51">Click to see more information</NuxtLink></div>
            </li>
          </ul>

          <ul>
            <li><span></span>
                <div class="title">
                  <h3>1903</h3>
                </div>
                
                  <div class="info">
                  <p class="detail">This election was start at 1903-12-16</p>
                </div>

                <div class="link"><NuxtLink :to="'/speeches/' + 59">Click to see more information</NuxtLink></div>
            </li>
          </ul>

          <ul>
            <li><span></span>
                <div class="title">
                  <h3>1906</h3>
                </div>
                
                  <div class="info">
                  <p class="detail">This election was start at 1906-12-12</p>
                </div>

                <div class="link"><NuxtLink :to="'/speeches/' + 42">Click to see more information</NuxtLink></div>
            </li>
        </ul>
      
            <h5 v-if="$fetchState.pending">Just a monent...</h5>
            <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
      <!-- This is the error feedback -->

        <ul v-for="election in elections" :key="election.id">
            <li><span></span>
                <div class="title">
                  <h3>{{  election.name  }}</h3>
                </div>
                
                  <div class="info">
                  <p class="detail">This election was start at {{ election.date }}</p>
                </div>

                <div class="link"><NuxtLink :to="'/speeches/' + election.id">Click to see different information</NuxtLink></div>
            </li>
        </ul>
      </div>

</template>

<script>
 export default {
   data() {
        return {
         elections: [],
        }
   },

   async fetch() {
    // This is how to fetch the API

    const apiData = await fetch('https://electionspeeches.moadoph.gov.au/api/elections.json')
		.then((response) =>
			response.json()
		)
		console.log(apiData)

    this.elections = apiData;

   }
  }
</script>

<style>

.container {
  margin: 40px 40px;
}

/* Error text */

.container h5 {
  font-size: 70px;
  color: #fff;
}

/* Timeline */

.container ul {
  list-style: none;
  margin: 0;
  padding: 0;
  position: relative;
}

.container ul:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 2px;
  height: 100%;
  border: 2px dashed #aaa;
}

/* Data container */

.container ul li {
  margin: 50px 60px;
  position:  relative;
  padding: 20px;
  background-color: #1995bb;
  color: white;
  border-radius: 10px;
  margin-bottom: 20px;
}

.link a {
  padding: 1em;
  color: #ffffff;
}
.link a:hover {
  color:#000000;
}

/* Dots between the line */

.container ul li span {
  content: '';
  position: absolute;
  top: 0;
  left: -60px;
  width: 0px;
  height: 100%;
  border: 1px dashed #aaa;
}

.container ul li span:before, .container ul li span:after {
  content: '';
  width: 10px;
  height: 10px;
  border: 2px solid #aaa;
  position: absolute;
  border-radius: 50%;
  left: -5px;
  background: #fff;
}

.container ul li span:before:hover, .container ul li span:after:hover {
  background:#eb2121;
}

.container ul li span:before {
  top: -10px;
}

.container ul li span:after {
  top: 100%;
}

/* Seperate with v-html <P> */

.info .detail {
  margin: 0;
}

/* Reponsive */
@media (min-width:640px) and (max-width: 1024px) {

.container h5 {
  font-size: 50px;
  color: #fff;
}

.info {
  font-size: 5px;
}

.link a {
  padding: 0em;
}

}

@media (max-width: 639px) {

.container h5 {
  font-size: 40px;
  color: #fff;
}

.info {
  display: none;
}

.link a {
  padding: 0em;
}

}

</style>