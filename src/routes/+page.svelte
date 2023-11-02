<script lang="ts">
  import Editor from '$widgets/editor.svelte';

  const text: string = 'Visit kit.svelte.dev to read the documentation';
</script>

<div class="w-full h-full flex flex-col items-center">
  <Editor />

  <h1>Welcome to your library project</h1>
  <p>Create your package using @sveltejs/package and preview/showcase your work with SvelteKit</p>

  <a class="flex button text-3xl" href="https://kit.svelte.dev">{text}</a>
</div>

<style>
  .button {
    padding: 0.5rem;

    border: 1px solid rgb(0, 0, 0);
    border-radius: 0.25rem;

    color: rgb(0, 0, 0);

    font-size: 2rem;

    cursor: pointer;
  }
</style>
