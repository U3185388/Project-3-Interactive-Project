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

      <Candidate />

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
import Candidate from '~/components/Candidate.vue';
 export default {
    data() {
        return {
            candidates: [],
        };
    },
    async fetch() {
        // This is how to fetch the API
        const apiData = await fetch("https://electionspeeches.moadoph.gov.au/api/candidates.json")
            .then((response) => response.json());
        console.log(apiData);
        this.candidates = apiData;
    },
    components: { Candidate }
}
</script>
