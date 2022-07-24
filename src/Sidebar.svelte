{#if show}
<div class="modal-overlay" data-close on:click={overlay_click} transition:fade={{duration: 150}}></div>
  <nav transition:fly={{x: 250, opacity: 1}}>
    <button on:click={() => { show = false;}}>&times;</button>
  </nav>
{/if}

<Modal bind:show={modal_show} />

<script>
import { fly } from 'svelte/transition';
import Modal from './Modal.svelte';
import { fade } from 'svelte/transition';
function overlay_click(e) {
    if ('close' in e.target.dataset)
        show = false;
}
export let show = false;
let modal_show = false;
</script>
		
<style>
	.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  z-index: 10;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
nav {
  position: fixed;
  top: 0;
  right: 0;
  height: 100%;
  padding: 2rem 1rem 0.6rem;
  border-left: 1px solid #aaa;
  background: #fff;
  overflow-y: auto;
	width: 350px;
	z-index: 100;
}
</style>