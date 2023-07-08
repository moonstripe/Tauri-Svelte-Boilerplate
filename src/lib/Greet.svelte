<script lang="ts">
	import { invoke } from '@tauri-apps/api/tauri';

	let name: string = '';
	let greetMsg: string = '';

	const greet = async () => {
		greetMsg = await invoke('greet', { name });
	}
</script>

<div>
	<input id="greet-input" placeholder="Enter a name..." bind:value={name} />
	<button on:click={greet}>Greet</button>
	<p>{greetMsg}</p>
</div>
