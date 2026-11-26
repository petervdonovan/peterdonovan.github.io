<script setup>
import portrait from './assets/peter-donovan-profile-photo.jpg'
import publications from './publications.js'
</script>

<template>
  <main>
    <header class="profile">
      <h1>Peter Donovan</h1>
      <img :src="portrait" alt="Portrait of Peter Donovan" width="938" height="937">
      <div>
        <p>I am an undergraduate at UC Berkeley, and I currently work with <a href="https://gireejar.github.io/">Prof. Gireeja Ranade</a> on automated formal proof synthesis with applications in education and technical communication. The driving educational application is currently the <a href="https://leantutor.org/">LeanTutor</a> project.</p>
        <p>Prior to this, I worked on real-time task scheduling, primarily as part of the development of the <a href="https://www.lf-lang.org/community/">Lingua Franca</a> coordination language. For details about my recent industry experience in robotics (simulation, perception), see <a href="https://www.linkedin.com/in/peter-donovan-a41aa0166/">LinkedIn</a>.</p>
        <a href="mailto:peterdonovan@berkeley.edu">peterdonovan@berkeley.edu</a>
      </div>
    </header>

    <section class="projects" aria-labelledby="current-projects">
      <h2 id="current-projects">Current Projects</h2>
      <p><a href="https://petervdonovan.github.io/10-2-26-presentation/docs/">linalg-checker</a> — Lightweight checking for undergraduate-level finite-dimensional linear algebra.</p>
    </section>

    <section aria-labelledby="publications">
      <h2 id="publications">Publications</h2>
      <div v-for="{ year, papers } in publications" :key="year" class="publication-year">
        <h3>{{ year }}</h3>
        <ul role="list">
          <li v-for="paper in papers" :key="paper.url">
            <a class="paper-title" :href="paper.url">{{ paper.title }}</a>
            <p>
              <template v-for="(author, index) in paper.authors" :key="author">
                <strong v-if="author === 'Peter Donovan'">{{ author }}</strong><template v-else>{{ author }}</template>{{ index === paper.authors.length - 1 ? '' : index === paper.authors.length - 2 ? ', and ' : ', ' }}
              </template>{{ paper.authorNote ? ` (${paper.authorNote})` : '' }}.
            </p>
            <p><cite>{{ paper.venue }}</cite>, {{ paper.details }}.</p>
          </li>
        </ul>
      </div>
    </section>
  </main>
</template>

<style>
:root {
  font-family: system-ui, sans-serif;
  color: #1e2936;
  background: #fff;
  line-height: 1.6;
}

body {
  margin: 0;
}

main {
  max-width: 46rem;
  margin-inline: auto;
  padding: clamp(2rem, 6vw, 4.5rem) clamp(1.25rem, 5vw, 2rem);
}

h1,
h2,
h3,
p {
  margin: 0;
}

h1,
h2 {
  color: #16212d;
  line-height: 1.2;
  letter-spacing: -0.025em;
}

h1 {
  font-size: clamp(2rem, 6vw, 2.75rem);
}

h2 {
  font-size: 1.6rem;
}

h3 {
  font-size: 1.125rem;
  margin-bottom: 0.75rem;
}

a {
  color: #24578c;
  text-underline-offset: 0.18em;
  overflow-wrap: anywhere;
}

a:focus-visible {
  outline: 2px solid currentColor;
  outline-offset: 3px;
}

.profile {
  display: grid;
  grid-template-columns: 25% minmax(0, 1fr);
  gap: 1.25rem 1.5rem;
  align-items: center;
  padding-bottom: 2rem;
  margin-bottom: 2rem;
  border-bottom: 1px solid #dbe1e7;
}

.profile h1 {
  grid-column: 1 / -1;
  text-align: center;
}

.profile img {
  display: block;
  width: 100%;
  height: auto;
  border-radius: 0.5rem;
}

.profile p {
  margin-bottom: 0.55rem;
}

.projects {
  margin-bottom: 2rem;
}

.projects p {
  margin-top: 0.75rem;
}

.publication-year {
  margin-top: 1.5rem;
}

ul {
  display: grid;
  gap: 1.15rem;
  padding: 0;
  margin: 0;
  list-style: none;
}

.paper-title {
  font-weight: 650;
}

li p {
  color: #465361;
  font-size: 0.95rem;
  margin-top: 0.15rem;
}

@media (max-width: 36rem) {
  .profile {
    grid-template-columns: minmax(0, 1fr);
    gap: 1rem;
  }

  .profile img {
    max-width: calc(8rem / 3);
  }
}
</style>
