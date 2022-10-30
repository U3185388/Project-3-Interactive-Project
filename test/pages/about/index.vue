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
                About this website
            </h2></div>

            <div class="intro">
                <p>This website is a repository of information on speeches by successive Australian Prime Ministers. The homepage is a filter composed of elections or candidates, and jumps to the specified speech according to the elected candidate or designated candidate.</p>
            </div>

            <div class="describe">
                <p>The homepage categorizes elections or candidates in the form of a timeline, and filters the categories through the navigation on the right side of header, which improves the efficiency of user browsing and searching.
                    <br>Click to enter the slug page, the page will display the time, location and word number of the speech; Followed by the speech that the elector brought at that time
                    <br>Here is the APIs:
                    <br><ul>
                        <li><a href="https://electionspeeches.moadoph.gov.au/api/elections.json">https:<wbr>//electionspeeches<wbr>.moadoph<wbr>.gov<wbr>.au<wbr>/api<wbr>/elections<wbr>.json</a></li>
                        <li><a href="https://electionspeeches.moadoph.gov.au/api/candidates.json">https:<wbr>//electionspeeches<wbr>.moadoph<wbr>.gov<wbr>.au<wbr>/api<wbr>/candidates<wbr>.json</a></li>
                        <li><a href="https://electionspeeches.moadoph.gov.au/api/speeches.json">https:<wbr>//electionspeeches<wbr>.moadoph<wbr>.gov<wbr>.au<wbr>/api<wbr>/speeches<wbr>.json</a></li>
                    </ul>
                </p>
            </div>

            <div class="shame">
                <p>It's a pity that this page is for demonstration purposes only, as some features are not available because Nuxt. js cannot be implemented</p>
                <p>Please pay attention to the prompts on the timeline, some links do not lead to the correct information</p>
            </div>
        </div>

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

<style>

.content {
    margin: 60px 100px;
    background-color: rgb(240, 228, 176);
}

.content .info {
    text-align: center;
    margin-top: 2em;
}

.content .info h2 {
    color: #226A80;
    background-color: rgb(34, 168, 123);
    font-size: 32px;
    font-weight: 800;
    letter-spacing: 2px;
    line-height: 60px;
    margin-bottom: 30px;
    padding: 1em;
}

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

/* Reponsive */
@media (min-width:640px) and (max-width: 1024px) {
    ul {
    margin-left: -1em;

}

}

@media (max-width: 639px) {

    ul {
    margin-left: -1em;

}

}

</style>