<script lang="ts" context="module">
  export const load = () => {
    return {status: 404, error: new Error('Explicitly not found')}
  }
</script>