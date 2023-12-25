<script lang="ts" context="module">
  export const meta = {
    title: 'Form',
    component: Login
  };
</script>

<script lang="ts">
  import { Story } from '@storybook/addon-svelte-csf';
  import Login from '../../../routes/login/+page.svelte';
  import Signin from '../../../routes/signin/+page.svelte';
</script>

<Story name="Login">
  <Login />
</Story>

<Story name="Register">
  <Signin />
</Story>
