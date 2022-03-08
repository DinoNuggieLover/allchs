<script context="module">
/** @type {import('@sveltejs/kit').Load} */
export async function load({ params, fetch, session, stuff }) {
    let request = await fetch("/json/games.json");
    let games = await request.json();
    let game = games[params.slug];
    if (game && game.location) {
      return {
        props: {
          game: game.location
        }
      }
    } else {
      return {
        status: 404,
        error: "The game could not be found"
      }
    }
}
</script>

<script>
  export let game;
</script>

<svelte:head>
   <title>Game | All CHS</title>
</svelte:head>

<p>Location of Game: {game}</p>