<template>
    <div class="bio">
        <p>{{ candidate.name }}</p>
        <p>Does he/she won?{{ candidate_won_election }}</p>
    </div>
</template>

<script>
 export default {
  async fetch({ params }) {
    // This is how to fetch the API
    const page = await fetch(`https://electionspeeches.moadoph.gov.au/api/candidates/?slug=${params.slug}`).then((res) => {
            if (res.ok) {
                return res.json();
            }
            throw new Error(res.status);
        });
        const analysis = page[0].body;
        return { analysis, page };
   }
  }
</script>