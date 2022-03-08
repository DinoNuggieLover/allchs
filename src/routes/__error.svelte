<script context="module">
  /** @type {import('@sveltejs/kit').ErrorLoad} */
  export function load({ error, status }) {
    return {
      props: {
        status: status,
        message: error.message
      }
    };
  }
</script>

<script>
  export let status;
  export let message;
</script>

<div class="error">
  <h1 class="status"><b>{status}</b></h1>
  <p class="message">{message}</p>
</div>

<style>
  .error {
    padding-top: 10%;
  }
  .status, .message {
    text-align: center;
    word-break: normal;
  }
</style>