<template>

    <div class="container">
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

                <div class="link"><NuxtLink :to="'/speeches/' + election.id">Click to see more information</NuxtLink></div>
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

/* @media only screen and (min-width: 768px) {
  .timeline:before {
    content: "";
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 2px;
    height: 100%;
    background-color: gray;
  }
  .timeline ul li {
    width: 50%;
    position: relative;
    margin-bottom: 50px;
  }
  .timeline ul li:nth-child(odd) {
    float: left;
    clear: right;
    transform: translateX(-30px);
    border-radius: 20px 0px 20px 20px;
  }
  .timeline ul li:nth-child(even) {
    float: right;
    clear: left;
    transform: translateX(30px);
    border-radius: 0px 20px 20px 20px;
  }
  .timeline ul li::before {
    content: "";
    position: absolute;
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background-color: gray;
    top: 0px;
  }
  .timeline ul li:nth-child(odd)::before {
    transform: translate(50%, -50%);
    right: -30px;
  }
  .timeline ul li:nth-child(even)::before {
    transform: translate(-50%, -50%);
    left: -30px;
  }
  .timeline-content .date {
    position: absolute;
    top: -30px;
  }
  .timeline ul li:hover::before {
    background-color: aqua;
  }
} */
</style>