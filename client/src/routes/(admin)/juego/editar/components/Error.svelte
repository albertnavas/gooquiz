<script lang="ts">
	export let editSuccess: boolean
</script>

<div class="mx-auto w-5/6">
	<div class="card text-neutral-content">
		{#if !editSuccess}
			Disculpas! Error al guardar las preguntas
		{/if}
	</div>
</div>
