<script lang="ts">
  import { writable } from 'svelte/store';

  import { Button, Content, Form, FormGroup, TextInput, Tile } from 'carbon-components-svelte';

  const username = writable('');
  const password = writable('');

  function handleLogin(e: any) {
    e.preventDefault();
    console.log('Logging in with:', { username, password });
  }
</script>

<Content>
  <Tile>
    <h2>Login</h2>
    <Form on:submit={handleLogin}>
      <FormGroup legendText="">
        <TextInput
          id="username"
          labelText="Username"
          value={$username}
          on:change={(e) => username.set(e.target.value || '')}
          required
        />
        <TextInput
          id="password"
          labelText="Password"
          type="password"
          value={$password}
          on:change={(e) => password.set(e.target.value || '')}
          required
        />
      </FormGroup>
      <Button type="submit" kind="primary">Log In</Button>
    </Form>
  </Tile>
</Content>
