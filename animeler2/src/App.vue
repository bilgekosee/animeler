<template>
  <div>
    <header>
      <h1>Sonsuz Anime</h1>
    </header>
    <main>
      <post v-for="(anime, i) in anime_list" :key="i" :anime="anime" />
    </main>
  </div>
</template>

<script>
import Post from "./components/Post.vue";
export default {
  name: "App",
  data() {
    return {
      anime_list: [],
    };
  },
  components: {
    // eslint-disable-next-line vue/no-unused-components
    Post,
  },
  methods: {
    getAnime() {
      const anime_titles = [
        "Naruto",
        "Demon Slayer",
        "Dragon Ball",
        "My Hero Acadmy",
        "Angel Of Death",
        "Tokyo Ghoul",
        "Kotaro Lives Alone",
        "Attack on Titan",
        "Castlevania",
        "Saiki Ka",
        "Guilty Crown",
      ];
      const anime = [];
      for (let i = 0; i < 10; i++) {
        anime.push({
          title: anime_titles[Math.floor(Math.random() * anime_titles.length)],
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        });
      }
      return anime;
    },
    handleScroll() {
      if (
        window.scrollY + window.innerHeight >=
        document.body.scrollHeight - 50
      ) {
        const new_anime = this.getAnime();

        this.anime_list = [...this.anime_list, ...new_anime];
      }
    },
  },
  mounted() {
    this.anime_list = this.getAnime();
    window.addEventListener("scroll", this.handleScroll);
  },
};
</script>

<style>
* {
  margin: 0;
  box-sizing: border-box;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #132a13;
  background-color: #004d40;
  margin-top: 60px;
  max-height: 100vh;
  padding-top: 3rem;
}
header h1:hover {
  color: #a3b18a;
  text-align: center;
}
header {
  margin-bottom: 2rem;
}
main {
  padding: 0 2rem;
  max-width: 640px;
  margin: 0 auto;
}
</style>
