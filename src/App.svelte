<button on:click={() => sidebar_show = !sidebar_show}>Toggle Sidebar</button>

<Sidebar bind:show={sidebar_show} />

<script>
import Sidebar from './Sidebar.svelte';
let sidebar_show = false;
</script>