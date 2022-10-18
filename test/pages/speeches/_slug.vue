<template>
    <section id="slug">
    <!-- Page style -->

    <div class="header">
      <NuxtLink to="/candidate">Back to Home page</NuxtLink>
    </div>

    <div v-html="body"></div>

</section>
</template>


<script>
 export default {
  async fetch({ params }) {
    // This is how to fetch the API
    const page = await fetch(`https://electionspeeches.moadoph.gov.au/api/speeches/${params.slug}.json`).then((res) => {
            if (res.ok) {
                return res.json();
            }
            throw new Error(res.status);
        });
        const body = page.body;
        console.log(body)
        return { body, page };
        
   }
  }
</script>