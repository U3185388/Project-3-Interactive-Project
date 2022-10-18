<template>
    <div class="message" :key="speech.id">
      <span>{{ speech.location }}</span>
      <span>{{ speech.title }}</span>
    </div>

</template>

<script>
 export default {
  async fetch({ params }) {
    // This is how to fetch the API
    const page = await fetch(`https://electionspeeches.moadoph.gov.au/api/speeches/?slug=${params.slug}`).then((res) => {
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