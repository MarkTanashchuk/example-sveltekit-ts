<script lang="ts" context="module">
  import Navigation from './index.svelte';

  export const meta = {
    title: 'Navigation',
    component: Navigation
  };
</script>

<script lang="ts">
  import { Story } from '@storybook/addon-svelte-csf';
</script>

<Story name="Default">
  <Navigation>
    <h1>Welcome</h1>
  </Navigation>
</Story>
