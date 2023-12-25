<script>
  import 'carbon-components-svelte/css/g10.css';
  import '../app.css';

  import { Column, Content, Grid, Row } from 'carbon-components-svelte';
</script>

<Content>
  <Grid>
    <Row>
      <Column>
        <slot />
      </Column>
    </Row>
  </Grid>
</Content>
