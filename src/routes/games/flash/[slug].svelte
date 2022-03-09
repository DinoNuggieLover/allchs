<script context="module">
/** @type {import('@sveltejs/kit').Load} */
export async function load({ params, fetch, session, stuff }) {
    let request = await fetch("/json/games.json");
    let games = await request.json();
    for (let i = 0; i < games.length; i++) {
      if (games[i].id == params.slug) {
        return {
          props: {
            game: games[i]
          }
        }
      }
    }
    return {
      status: 404,
      error: "The Flash Game Could Not Be Found"
    }
}
</script>

<script>
  export let game;
</script>

<svelte:head>
   <title>{game.title} | All CHS</title>
</svelte:head>
<h1>{game.title}</h1>
<p>Source of Game: {game.source}</p>