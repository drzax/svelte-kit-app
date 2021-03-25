<script context="module">
  export async function load({
    page: {
      params: { spread },
    },
  }) {
    console.log('spread :>> ', spread);
    if (spread === '404') {
      return;
    }
    return { props: { spread } };
  }
</script>

<script>
  import { page } from '$app/stores';
  export let spread;
</script>

<p data-source="load">{spread}</p>
<p data-source="store">{$page.params.spread}</p>
