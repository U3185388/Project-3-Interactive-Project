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
        <!-- Header -->

		<div class="content">
            <div class="info"><h2 class="message">
                {{ apiData.title }}
                {{ apiData.location }}
                {{ apiData.analysis.num_words }}
            </h2></div>
            <div class="p" v-html="apiData.body"></div>
        </div>
        <!-- Body -->

        <footer class="distributed">
            <div class="left">
                <h3>Created by Jacob</h3>
            </div>

            <div class="middle">
                <p>@University of Canberra</p>
            </div>
        </footer>
        <!-- Footer -->

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

.content {
    margin: 60px 100px;
    background-color: rgb(240, 228, 176);
}

.content .info {
    text-align: center;
    margin-top: 2em;
}

.content .info .message {
    color: #226A80;
    background-color: rgb(34, 168, 123);
    font-size: 32px;
    font-weight: 800;
    letter-spacing: 2px;
    line-height: 60px;
    margin-bottom: 30px;
    padding: 1em;
}

/* Fix v-html (speech body) */

p {
    margin-left: 3em;
    margin-right: 3em;
    padding: 1em;
}

ul {
    margin-left: 3em;
    padding: 1em;
}

ul li {
    margin-bottom: 1em;
    list-style-type: none;
}

ol {
    margin-left: 3em;
    padding: 1em;
}

ol li {
    margin-bottom: 1em;
    list-style-type: none;
}

h2 {
    margin-left: 2em;
    margin-right: 3em;
    padding: 1em;
}

/* Reponsive */
@media (min-width:640px) and (max-width: 1024px) {

.content .info .message {
    font-size: 2em;
    letter-spacing: 1px;
    line-height: 1em;
    margin-bottom: 1em;
    padding: 1em;
}

}

@media (max-width: 639px) {

.content .info {
    text-align: center;
    margin-top: 0.5em;
}

.content .info .message {
    font-size: 1em;
    letter-spacing: 1px;
}

}

</style>