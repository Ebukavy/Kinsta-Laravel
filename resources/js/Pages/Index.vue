<script setup>
  import KinstaLayout from "../Layouts/KinstaLayout.vue";
  import { Link } from "@inertiajs/inertia-vue3";

  defineProps({
    articles: Object,
  });
</script>

<template>
  <header>
    <h1>Kinsta Blog</h1>
  </header>

  <main>
    <h2>Read our latest articles</h2>

    <section>
      // Looping over articles
      <article v-for="article in articles":key="article.id">
        <div>
          <img src="/images/kinsta-logo.png" alt="Article thumbnail" />
        </div>

        <h3>{{article.title}}</h3>
        <p>{{article.excerpt}}</p>

        <Link
            :href="'/posts/' + article.id"
            class="text-indigo-600 hover:text-indigo-800 w-fit self-end font-semibold"
            >Read more
        </Link>

      </article>
    </section>      
  </main>

  <footer>
    <h2>Join our Newsletter</h2>

    <input type="email" />
  </footer>
</template>