<script lang="ts">
  import Header from '$lib/ErrorHeader.svelte'
  export let error: Error;
</script>

<Header/>
<div>{error.message}</div>
<a href="/">home</a>
<style>
  div {
    background: pink;
  }
</style>