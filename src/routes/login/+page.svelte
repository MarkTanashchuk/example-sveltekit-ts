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

  const email = writable('');
  const password = writable('');

  function handleLogin(e: any) {
    e.preventDefault();
    console.log('Logging in with:', { email, password });
  }

  function handleSetEmail(e: any) {
    email.set(e.target.value || '');
  }

  function handleSetPassword(e: any) {
    password.set(e.target.value || '');
  }
</script>

<Content>
  <Tile>
    <h2>Login</h2>
    <Form on:submit={handleLogin}>
      <FormGroup class="stacked-form">
        <TextInput
          id="email"
          placeholder="Enter email..."
          value={$email}
          on:change={handleSetEmail}
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
