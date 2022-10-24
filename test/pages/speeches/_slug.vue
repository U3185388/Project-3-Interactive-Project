<template>

	<section>
        
        <div class="header">
            <h2>Welcome to Australian Prime Election Library</h2>
            <div class="navigation">
                <NuxtLink to="/candidate">See candidates</NuxtLink>
                <NuxtLink to="/">See elections</NuxtLink>
                <NuxtLink to="/about">About this website</NuxtLink>
            </div>
        </div>

		<div class="content">
            <div class="info"><h2>
                {{ apiData.title }}
                {{ apiData.location }}
                {{ apiData.analysis.num_words }}
            </h2></div>
            <div class="p" v-html="apiData.body"></div>
        </div>

	</section>
</template>


<script>
// need to use asyncData request instead of await fetch
export default {
    async asyncData({ params }) {
        // get the speech from the id in url
        const speech = await fetch(`https://electionspeeches.moadoph.gov.au/api/speeches/${params.slug}.json`).then((res) => {
            if (res.ok) {
                return res.json();
            }
            throw new Error(res.status);
        });
        // see the contents
        console.log(speech);
        // now we've got the data, lets create a new variable to hold just the api data
        const apiData = speech;
        // return the api data so we can access it
        return { apiData };
    }
}
</script>

<style>

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Poppins", sans-serif;
}

section {
    position: relative;
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    background-color: rgb(16, 75, 236);
}

.header {
    position: relative;
    top: 0;
    width: 100%;
    padding: 40px 100px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: rgb(236, 185, 44);
}

.header h2 {
    position: relative;
    color: #000;
    font-size: 30px;
    text-decoration: none;
    text-transform: uppercase;
    font-weight: 800;
    letter-spacing: 1px;
}

.header .navigation {
    color:#000;
    background: #fff;
    text-decoration: none;
    font-weight: 500;
    letter-spacing: 1px;
    padding: 2px 15px;
    border-radius: 20px;
}

.header .navigation a:not(:last-child) {
    margin-right: 30px;
}

.header .navigation a:hover {
    background: #fff;
}

.content {
    margin: 60px 100px;
    background-color: rgb(240, 228, 176);
}

.content .info h2 {
    color: #226A80;
    background-color: rgb(34, 168, 123);
    font-size: 40px;
    font-weight: 800;
    letter-spacing: 2px;
    line-height: 60px;
    margin-bottom: 30px;
}
    
</style>