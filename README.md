# Project-3-Interactive-Project
This is a reconfiguration based on the [Project-2](https://github.com/U3185388/Project-2-Basic-Web-Application-u3185388).
<br>The same work with [Project-2](https://github.com/U3185388/Project-2-Basic-Web-Application-u3185388), there are more styles and a more minimalistic local file than [Project-2](https://github.com/U3185388/Project-2-Basic-Web-Application-u3185388).

## Submission details
Since the commit is confusing, so here are the brief explainations here

<br>**The first submission**: Fixed API usage and formatting of HTML pages, currently stalled by Sulg pages failing to render data.

**Second sumbission**: Complete the addition of basic content; But there are still problems that affect the execution.

**Third submission**: Change other way to fix the problems, and create the responsive.

## Run the project
There are two ways to run this project
### Run locally
Use `cd test` on the terminal to locate the root, and choose any way to start hosting:
```
yarn dev
```
or
```
npm run dev
```
### Run online
Click here to see on [codesandbox](https://codesandbox.io/p/github/U3185388/Project-3-Interactive-Project/main?workspace=%257B%2522activeFileId%2522%253Anull%252C%2522openFiles%2522%253A%255B%255D%252C%2522sidebarPanel%2522%253A%2522EXPLORER%2522%252C%2522gitSidebarPanel%2522%253A%2522COMMIT%2522%252C%2522sidekickItems%2522%253A%255B%257B%2522type%2522%253A%2522UNASSIGNED_PORT%2522%252C%2522port%2522%253A3000%252C%2522url%2522%253A%2522ns6kp3-3000.preview.csb.app%2522%252C%2522key%2522%253A%2522cl9ti93o3027r3n6hapljwd9q%2522%252C%2522isMinimized%2522%253Afalse%257D%252C%257B%2522type%2522%253A%2522TERMINAL%2522%252C%2522shellId%2522%253A%2522cl9thyvjp0016lpgfeyh9d31z%2522%252C%2522key%2522%253A%2522cl9thyvvq007s3n6hysbge4zj%2522%252C%2522isMinimized%2522%253Afalse%257D%255D%257D). If there is an error on the preview page, please refresh it in the preview.

## Rationale
Working on nuxt again, I become more proficient and more knowledgeable about plugins for front-end frameworks. Without the rush I had last time, I was able to spend more time fixing and finding issues left over from [Project-2](https://github.com/U3185388/Project-2-Basic-Web-Application-u3185388), and a more interesting looking web page. This time the theme is based on the API provided by [Federal Election Speeches](https://electionspeeches.moadoph.gov.au/explore) to create a web page that can be browsed in the form of a timeline. The home page can switch between elections and candidates, providing more convenient filters. The slug page shows speeches by the winner of the election or by a specific candidate.
<br>
#### Compare with the Project 2
**More reasonable and concise local files**: No more messy CSS; More refined headers and footers; More intuitive comments.
<br>**More refined content display**: Modification of v-html, and modification of content containers
#### Home page
The **Election** filter.![election](https://user-images.githubusercontent.com/53715219/198817832-ab9eba79-cb1c-4c5f-81df-5f83d052155e.png)
The **Candidate** filter.![candidate](https://user-images.githubusercontent.com/53715219/198817866-08d30e42-bc46-427b-8f76-90853ea6bfe2.png)
The top is the date/candidate; the middle is the details, that is, the specific time/candidate details; the bottom is the instruction, and a link is provided to jump.
 <br>
#### Slug page
![slug](https://user-images.githubusercontent.com/53715219/198818103-7bd80de2-009f-4ee6-b0a5-1e74fcf2b9b0.png)
The green container at the top shows the name and location, and the bottom is the speech.

#### About page
![about](https://user-images.githubusercontent.com/53715219/198818174-68ee9e47-e1c8-45b8-a116-350faf6ebb4d.png)
Add some brief introduction.

#### Header on responsive page
![responsive](https://user-images.githubusercontent.com/53715219/198819141-c71ad8c4-799a-4fe7-ba00-d2431c7dae3c.png)
With hover effect, and the title disappears on small screens

#### Footer
![footer](https://user-images.githubusercontent.com/53715219/198819146-2f1264f2-0522-4174-9ce0-5ba62ebf6228.png)
A more solemn-looking footer

## The regret left
The biggest regret is not being able to achieve **my plan**: <br>
**Home page** - Create a more refined timeline. The election screening section provides jump links for the winners and losers; the candidate screening section displays two candidates based on the timeline.
<br>**Slug page** - According to the candidates for the election, provide their speeches and display them by clicking on one; switch the background color according to their party.
<br>Provide **search function**. 
<br>However, these cannot be achieved due to insufficient personal ability ~~(perhaps the limitation of framework ability)~~.

## Reflection
After these two assignments, I have a general understanding of the front-end framework, and I also plan to learn VUE and React in the future to improve my front-end capabilities. It is a pity to have regrets, but it is precisely because of regrets that there will be growth, and there will be a plan to "do it well next time".
<br>At the end of this semester, I realized that when I was programming C# in Unity, I would take the initiative to add comments. I seem to have developed such a good habit unknowingly. Even though I am still not proficient in JavaScript, and even though I'm still not programming fully autonomously, I know that I am making progress. <br>Just for the record, and looking back at this document five years later, I will ask myself:
- **Are you proficient in web programming?**
- **Have you mastered Vue and React yet?**
- **Have you embarked on the path of a full stack developer? Or that I am already doing what position I wish to be. .**
