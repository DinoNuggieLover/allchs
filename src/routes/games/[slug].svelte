<script context="module">
/** @type {import('@sveltejs/kit').Load} */
export async function load({ params, fetch, session, stuff }) {
    let request = await fetch("/json/games.json");
    let games = await request.json();
    for (let i = 0; i < games.length; i++) {
      let game = games[i];
      if (game.id == params.slug) {
        game.source = "https://example.com";
        return {
          props: {
            game: game
          }
        }
      }
    }
    return {
      status: 404,
      error: "The Game Could Not Be Found"
    }
}
</script>

<script>
  export let game;
</script>

<svelte:head>
   <title>{game.title} | All CHS</title>
</svelte:head>

<iframe src={game.source}/>

<style>
iframe {
    width: 100%;
    background: white;
    border: none;
    height: 26.25em; /* TODO: Fix This */
}
</style>