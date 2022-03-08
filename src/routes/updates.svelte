<svelte:head>
  <title>Updates | All CHS</title>
</svelte:head>

<script context="module">
    /** @type {import('@sveltejs/kit').Load} */
    export async function load({ params, fetch, session, stuff }) {
        let request = await fetch("/json/updates.json");
        let json = await request.json();
        return {
            status: request.status,
            props: {
                updates: json,
            },
        };
    }
</script>

<script>
  export let updates;
</script>

<div class="banner">
    <section>
        <h1>Updates</h1>
    </section>
</div>
<div>
  <ul>
  {#each updates as update}
    <li>{update}</li>
  {/each}
  <ul/>
</div>

<style>
.banner {
    background: url(/image/pattern.png) repeat;
    background-size: 54px;
    width: var(--width);
    padding: 60px calc(50% - calc(var(--width) / 2));
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: #FFF;
    box-sizing: content-box;
}
</style>