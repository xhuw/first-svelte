<script>
	import { invoke } from '@tauri-apps/api/tauri';

	let name = '';
	let message = 'Hi!';

	async function greet() {
		message = await invoke('greet', { name });
	}
</script>

<input bind:value={name} />
<button on:click={greet}> get greeting </button>

<p>{message}</p>
