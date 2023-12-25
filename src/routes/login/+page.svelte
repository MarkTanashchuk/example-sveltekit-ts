<script lang="ts">
  import { writable } from 'svelte/store';

  import {
    Button,
    Content,
    Form,
    FormGroup,
    PasswordInput,
    TextInput,
    Tile
  } from 'carbon-components-svelte';

  const username = writable('');
  const password = writable('');

  function handleLogin(e: any) {
    e.preventDefault();
    console.log('Logging in with:', { username, password });
  }

  function handleSetUsername(e: any) {
    username.set(e.target.value || '');
  }

  function handleSetPassword(e: any) {
    username.set(e.target.value || '');
  }
</script>

<Content>
  <Tile>
    <h2>Login</h2>
    <Form on:submit={handleLogin}>
      <FormGroup class="stacked-form">
        <TextInput
          id="username"
          placeholder="Enter username..."
          value={$username}
          on:change={handleSetUsername}
          required
        />
        <PasswordInput
          id="password"
          placeholder="Enter password..."
          value={$password}
          on:change={handleSetPassword}
          required
        />
      </FormGroup>
      <Button type="submit" kind="primary">Log In</Button>
    </Form>
  </Tile>
</Content>

<style>
  :global(.stacked-form) {
    display: flex;

    flex-direction: column;

    gap: 2rem;

    margin: 2rem 0;
  }
</style>
