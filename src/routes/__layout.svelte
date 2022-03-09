<svelte:head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width initial-scale=1">
    <title>All CHS</title>
  </svelte:head>
  <body>
      <div class="wip">
        All CHS is not yet finished. Please bookmark this page and comeback later when this site is fully functional.
      </div>
      <nav>
        <a href="/"> <img border="0" class="logo-img" src="/image/logo.png" height="110" width="110"></a>
        <ul>
          <li><a href="/">Home</a></li>
          <li><a href="/games">Games</a></li>
          <li><a href="/chat">Chat</a></li>
          <li><a href="/updates">Updates</a></li>
        </ul>

      </nav>
      <slot/>
        <footer>
    <nav>
      <section>
         <a href="/credits">Credits</a>
         <a href="https://github.com/DinoNuggieLover/allchs">Github</a>
      </section>
      <section>
         <span>All CHS 2022</span>
      </section>
   </nav>
</footer>
  </body>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
body {
    --border-color:rgb(255, 255, 255, .2);
    --header-background: #181818;
    --text-color: #FFF;
    --secondary-color: dodgerblue;
    background: #121212;
    --header-shadow: rgba(0, 0, 0, 0.1) 0px 5px 10px 0px;
    --scrollbar-thumb-color: rgb(32, 148, 252, 0.3);
    --scrollbar-track-color: #000;
    --width: 80%;
    font-family: Roboto;
    color: var(--text-color);
    margin: 0;
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}
  
* {
  margin: 0;
  padding: 0;
  font-family: 'Poppins','sans-serif';
}
  
.wip {
  margin: auto;
  width: 100%;
  text-align: center;
}
  
* {
    box-sizing: border-box;
    scrollbar-width:thin;
    scrollbar-color:var(--scrollbar-thumb-color) var(--scrollbar-track-color);
}

::-webkit-scrollbar {
    width: 7px;
}
::-webkit-scrollbar-track {
    background: var(--scrollbar-track-color)
}
::-webkit-scrollbar-thumb {
    background: var(--scrollbar-thumb-color);
}

nav {
  display: flex;
  align-items: center;
  padding: 0px 1%;
}

nav .menu-img {
  width: 25px;
  margin-right: 20px;
}

nav .logo-img {
  width: 160;
  cursor: pointer;
  padding: 20px;
}

nav ul{
  flex: 1;
  text-align: right;
}

nav ul li{
  display: inline-block;
  list-style: none;
  margin: 0 20px;
}

nav ul li a {
  text-decoration: none;
  color: #fff
}
  
.menu-img {
  color: white;
  padding: 16px;
  font-size: 16px;
  border: none;
}
  
body {
    --width: 93%;
}
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

.faq {
    display: grid;
    margin: 15px auto;
    width: var(--width);
    grid-template-columns: auto auto;
    justify-content: space-between;
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
    
.faq section {
    width: 595px;
    margin: 8px 0px;
}

  @media only screen and (max-width: 1535px) {
      .faq section {
        width: 90%;
      }
    }
    @media only screen and (max-width: 545px) {
      .faq h1 {
        font-size: 25px;
      }
    }
      
    @media only screen and (max-width: 890px) {
      .faq {
          grid-template-columns: auto;
      }
    }
  footer {
    margin-top: auto;
    width: 100%;
    height: 80px;
    display: flex;
    justify-content: center;
    align-items: center;
}
nav section:first-child *:first-child {
    margin-left: 0;
}

nav section:last-child *:last-child {
    margin-right: 0;
}

a {
    color: var(--secondary-color);
    text-decoration: underline;
    cursor: pointer;
}

nav a {
    margin: 0 15px;
    text-decoration: none;
    color: var(--text-color);
    font-size: 15px;
}
nav {
    display: flex;
    margin: 0 auto;
    width: var(--width);
    height: 80px;
    justify-content: space-between;
    align-items: center;
}
  
nav a:hover {
    text-decoration: underline;
}
footer nav a, footer nav span {
    font-size: 14px;
    color: var(--text-color);
}
</style>