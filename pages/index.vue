<script setup>
// import { roster } from '../data/roster-w22';
import { roundOne, roundTwo } from "../data/finals-f23.js";
const rounds = [
  {
    speakers: roundOne,
    start: "9am",
    container: "round1",
  },
  {
    speakers: roundTwo,
    start: "10:30am",
    container: "round2",
  },
];
</script>

<template>
  <div class="page-wrapper">
    <header>
      <img src="/images/sait-logo.png" alt="SAIT Logo" />
      <div>
        <h1>SAIT Web Developer Fast Track</h1>
        <h2>Final Presentations - December 13, 2023</h2>
      </div>
    </header>
    <main>
      <h3>Introductions</h3>
      <ul class="overview">
        <li>
          <a href="https://www.linkedin.com/in/tony-grimes-778ba135/"
            >Tony Grimes</a
          >: Lead Instructor
        </li>
        <li>
          <a href="https://www.linkedin.com/in/ashlyn-knox13/">Ashlyn Knox</a>:
          Co-Instructor
        </li>
        <li>
          <a href="https://www.linkedin.com/in/dasachadwick/">Dasa Chadwick</a>:
          Career and Consulting Instructor
        </li>
        <li>
          <a href="https://www.linkedin.com/in/terry-o-ba343b1b5"
            >Terry O'Dwyer</a
          >: Work Integrated Learning Coordinator
        </li>
        <li>
          <a href="https://www.linkedin.com/in/amosngai">Amos Ngai</a>: Academic
          Chair, School of Advanced Digital Technology
        </li>
      </ul>
      <h3>Program Overview</h3>
      <ul class="overview">
        <li><em>Tools</em>: Git/GitHub, npm, VS Code, Postman</li>
        <li>
          <em>Development</em>: HTML/CSS/JS, Svelte/SvelteKit, tailwindCSS,
        </li>
        <li><em>Data:</em>Supabase (Postgres), and Directus (CMS)</li>
        <li><em>Deployment</em>: GitHub, Netlify</li>
        <li><em>Design</em>: Figma, Figjam, GIMP</li>
      </ul>

      <Presentation
        v-for="(round, index) in rounds"
        :key="round.id"
        :round="round"
        :index="index"
      >
        <slot></slot>
      </Presentation>
      <h3 class="rounds">Thank you for joining us!</h3>
      <p>Help yourself to pizza and refreshments</p>
    </main>
  </div>
  <!-- <RosterCard v-for="student in roster" :key="student.id" :student=student>
    <slot></slot>
  </RosterCard> -->
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&family=Raleway:wght@300&display=swap");

/* Comment out for live site */
/* body {
  margin-bottom: 50vh;
}
.presentation {
  margin-bottom: 6em;
  min-height: 100vh;
}
h3.rounds {
  margin: 40vh 0;
}
h3.open {
  margin-top: 50vh;
} */
/* End comment */

/* Font */

body {
  font-family: "Open Sans", sans-serif;
  font-weight: 300;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Raleway", sans-serif;
  font-weight: 300;
}

body {
  font-size: 20px;
  margin-bottom: 15rem;
}

h1,
h2,
h3,
h4,
h5,
h6,
p {
  margin: 0;
  line-height: 1;
  text-align: center;
}

li {
  margin: 0;
  line-height: 1;
}

ul {
  list-style-type: none;
  padding-left: 0;
}

.page-wrapper {
  max-width: 70ch;
  margin: auto;
  padding: 1rem;
}

.page-wrapper > header {
  display: flex;
  align-items: center;

  border-bottom: 1px solid #aaa;
  padding: 1em;
  margin-bottom: 2em;
}

.page-wrapper > header img {
  width: 150px;
}

.page-wrapper > header div {
  flex-grow: 1;
}

.page-wrapper > header h1,
.page-wrapper > header h2 {
  margin: 0;
  text-align: center;
}

main {
  margin: auto;
  max-width: 62ch;

  display: flex;
  flex-direction: column;
  align-items: center;
}

main > h3 {
  font-size: 3rem;
  width: max-content;
  margin: 7rem 5rem auto;
  color: rebeccapurple;
  font-variant: small-caps;
}

.overview {
  text-align: left;
}
.overview li {
  font-size: 1.5rem;
  line-height: 1.5;
  list-style: initial;
}

.overview ul {
  padding-left: 2.5rem;
}

.presentation {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  margin: 5rem auto;
}
.presentation header {
  margin-bottom: 2rem;
  text-align: center;
  color: #666;
  margin: 0;
  width: 100%;
}

.presentation header h4 {
  font-size: 3rem;
  margin: 1rem;
}

.presentation header h5 {
  font-style: italic;
  font-size: 1.5rem;
}

figure {
  display: grid;
  grid-template-columns: 12em 1fr;
  grid-template-rows: 1fr;

  align-items: center;
  justify-content: center;

  min-width: 50ch;
  min-height: 12em;
  padding: 1rem;
  box-shadow: 1px 2px 10px 1px gray;
  border-radius: 4rem;
  background-image: radial-gradient(skyblue 30%, white 30.1%);
  background-size: 100em 100em;
  background-position: 52rem;
}

figure > img {
  grid-column: 1 / 2;
  grid-row: 1 / -1;

  width: 8em;
  height: 8em;
  margin: auto;
  object-fit: cover;

  border-radius: 50%;
}

.badges img {
  width: 2.25rem;
  margin: 0 0.7rem;
}

figcaption {
  text-align: center;
  margin: 0;
  padding: 0 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

figcaption header {
  font-size: 2.5rem;
  line-height: 1.2;
  color: #666;
  width: max-content;
  margin-top: 0.5rem;
  text-align: center;
}

figcaption p {
  margin: 1.25rem auto;
  margin-bottom: 0.5rem;
  line-height: 1.5;
}

.social ul,
.badges ul {
  display: flex;
  justify-content: center;
  margin: 1.25rem 0;
}

.badges ul {
  margin-bottom: 0.75rem;
}

.social li {
  font-size: 2rem;
  margin: 0.15rem 0.75rem;
}
.social li a {
  color: navy;
}

.group figure > img {
  width: 7em;
  height: 7em;
}

.group figure {
  padding: 0 1rem;
}

.group figcaption p {
  margin-bottom: 0.75rem;
  margin: 0;
}
</style>
