
<script lang="ts">
  import { onMount } from 'svelte';
  import api from '$lib/api';
  let status = 'loading';

  onMount(async () => {
    try {
      const res = await api.get('/health');
      status = res.data.status;
    } catch {
      status = 'error';
    }
  });
</script>

<h1>API Health: {status}</h1>
