<script>
  import Start from "$lib/Start.svelte";
</script>

<div id="app">
  <iframe
    title="laravel-app"
    id="app-iframe"
    src="http://127.0.0.1:8000"
    frameborder="0"
  />
  <div id="app-controllers">
    <Start />
  </div>
</div>

<style>
  #app {
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100vh;
    overflow: hidden;
  }
  #app-iframe {
    width: 100%;
    height: 100%;
  }
  #app-controllers {
    position: absolute;
    bottom: 0;
    width: 100vw;
    background: #000;
  }
</style>
