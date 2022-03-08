<script context="module">
    /** @type {import('@sveltejs/kit').Load} */
    export async function load({ params, fetch, session, stuff }) {
        let request = await fetch("/json/games.json");
        let json = await request.json();
        return {
            status: request.status,
            props: {
                games: json,
            },
        };
    }
</script>

<script>
    export let games; 
    /* TODO: Searching Games */
    let query;
    let thumbnails;
    let empty;
    function search() {
    //     let matches = 0;
    //     thumbnails.children.forEach((entry) => {
    //         const title = entry.getElementsByClassName("title")[0].textContent;
    //         if (!title.trim().toLowerCase().includes(query.trim().toLowerCase())) {
    //             entry.style.display = "none";
    //         } else {
    //             matches += 1;
    //            entry.style.removeProperty("display");
    //         }
    //     });
    //     if (!matches) {
    //         empty.style.display = "block";
    //     } else {
    //         empty.style.removeProperty("display");
    //     }
    }
</script>

<svelte:head>
  <title>Games | All CHS</title>
</svelte:head>

<div class="banner">
    <section>
        <h1>Games</h1>
        <span>This page reads JSON data from /static/json/games.json.
</span>
    </section>
</div>

<div id="content">
    <input on:keyup="{search}" bind:value="{query}" id="search" placeholder="Search For Games" />
    <div bind:this="{empty}" id="empty">
        <p>No Results Found</p>
    </div>
</div>

<div bind:this="{thumbnails}" id="thumbnails">
    {#each games as { image, pub, source, title }, i}
    <a class="thumbnail" href={pub}>
        <img src="/game/thumbnails/{image}" />
        <div class="title">{title}</div>
    </a>
    {/each}
</div>

<style>  .banner {
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

.button {
    padding: 15px 18px;
    display: inline-block;
    cursor: pointer;
    margin: 5px 6px;
    color: #FFF;
    text-decoration: none;
    border-radius: 3px;
    background: #242424;
    border: solid 1px #282828;
    font-family: inherit;
}
  
input {
    background: none;
    font-family: inherit;
    padding: 0px 10px;
    height: 48px;
    border: 1px solid var(--border-color);
    color: var(--text-color);
    border-radius: 3px;
    outline: none;
}
  
    .thumbnail {
        display: inline-block;
        width: 225px;
        height: 305px;
        border-radius: 5px;
        margin: 0 10px 20px 0;
        text-decoration: none;
        color: var(--text-color);
        cursor: pointer;
        border: 1px solid var(--border-color);
        background: var(--header-background);
    }

    .thumbnail img {
        width: 100%;
        height: 255px;
        border-radius: 5px 5px 0 0;
        border-bottom: 1px solid var(--border-color);
    }

    .thumbnail .title {
        width: 90%;
        text-align: center;
        margin: 0 auto;
        margin-top: 0px;
        margin-top: 12px;
        font-size: 14px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }

    #empty {
        display: none;
    }

    #search {
        width: 305px;
    }

    #content {
        margin: 15px auto;
        width: var(--width);
    }

    #thumbnails {
        margin: 15px auto;
        width: var(--width);
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }

    @media only screen and (max-width: 545px) {
        #search {
            width: 100%;
        }
    }
</style>