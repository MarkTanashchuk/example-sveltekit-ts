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
  const confirmPassword = writable('');

  const handleSignIn = (e: any) => {
    e.preventDefault();
    console.log('Signing in with:', { email, password, confirmPassword });
  };

  function handleSetEmail(e: any) {
    email.set(e.target.value || '');
  }

  function handleSetPassword(e: any) {
    email.set(e.target.value || '');
  }

  function handleSetPasswordConfirmation(e: any) {
    email.set(e.target.value || '');
  }
</script>

<Content>
  <Tile>
    <h2>Sign In</h2>
    <Form on:submit={handleSignIn}>
      <FormGroup class="stacked-form">
        <TextInput
          id="email"
          placeholder="Enter email..."
          type="email"
          value={$email}
          on:change={handleSetEmail}
          required
        />
        <PasswordInput
          id="password"
          placeholder="Enter password..."
          value={$password}
          tooltipAlignment="start"
          tooltipPosition="left"
          on:change={handleSetPassword}
          required
        />
        <PasswordInput
          id="confirmPassword"
          placeholder="Confirm password..."
          tooltipAlignment="start"
          tooltipPosition="left"
          value={$confirmPassword}
          on:change={handleSetPasswordConfirmation}
          required
        />
      </FormGroup>

      <Button type="submit" kind="primary">Sign In</Button>
    </Form>
  </Tile>
</Content>

<style>
  :global(.stacked-form) {
    display: flex;

    flex-direction: column;

    gap: 2rem;

    margin: 1rem 0;
  }
</style>
