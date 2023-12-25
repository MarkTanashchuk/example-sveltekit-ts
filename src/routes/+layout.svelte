<script>
  import { Client, cacheExchange, fetchExchange, setContextClient } from '@urql/svelte';
  import { Content } from 'carbon-components-svelte';

  import 'carbon-components-svelte/css/g10.css';
  import '../app.css';

  const client = new Client({
    url: import.meta.env.SANITY_GRAPHQL_PLAYGROUND_URL,
    exchanges: [cacheExchange, fetchExchange]
  });

  setContextClient(client);
</script>

<Content>
  <slot />
</Content>
