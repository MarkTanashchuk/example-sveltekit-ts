<script lang="ts">
  import { writable } from 'svelte/store';

  import { Button, Content, Form, FormGroup, TextInput, Tile } from 'carbon-components-svelte';

  const email = writable('');
  const password = writable('');
  const confirmPassword = writable('');

  const handleSignIn = (e: any) => {
    e.preventDefault();
    console.log('Signing in with:', { email, password, confirmPassword });
  };
</script>

<Content>
  <Tile>
    <h2>Sign In</h2>
    <Form on:submit={handleSignIn}>
      <FormGroup legendText="">
        <TextInput
          id="email"
          labelText="Email"
          type="email"
          value={$email}
          on:change={(e) => email.set(e.target.value || '')}
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
        <TextInput
          id="confirmPassword"
          labelText="Confirm Password"
          type="password"
          value={$confirmPassword}
          on:change={(e) => confirmPassword.set(e.target.value || '')}
          required
        />
      </FormGroup>
      <Button type="submit" kind="primary">Sign In</Button>
    </Form>
  </Tile>
</Content>
