<script lang="ts" context="module">
	import Title from './title.svelte';

	export const meta = {
		title: 'Title',
		component: Title
	};
</script>

<script lang="ts">
	import { Story, Template } from '@storybook/addon-svelte-csf';
</script>

<Template let:args>
	<Title {...args} />
</Template>

<Story name="No args" />
