<template>
  <div class="row-col">
    <h3>Button</h3>

    Button with an optional icon and different styles
    <Description compnent-name="Button"></Description>
    <Collapser :opened.sync="openUsage" label="Usage">
      <pre v-highlightjs="usage"><code class="html"></code></pre>
    </Collapser>

    <div style="line-height: 64px">
      <Button big>Big</Button>&nbsp;
      <Button icon="add">Left Icon</Button>&nbsp;
      <Button icon-right="expand_more">Right Icon</Button>&nbsp;
      <Button alt>Alt</Button>&nbsp;
      <Button icon="add" alt>Alt icon</Button>&nbsp;
      <Button plain>Plain </Button>&nbsp;
      <Button disabled>Disabled</Button>&nbsp;
      <Button icon="menu" big plain></Button>&nbsp;
      <Button icon="menu" big></Button>&nbsp;
      <Button mobile-bottom>Mobile Button</Button>&nbsp;
      <Button icon="menu" plain></Button>&nbsp;
      <Button icon="menu"></Button>&nbsp;
      <Button link="https://github.com/highqualitycode" icon="account_circle">Github</Button>&nbsp;
      <Button link="https://github.com/highqualitycode" icon="insert_chart" link-ico>Full Report</Button>&nbsp;
      <!-- OR -->
      <button class="button primary">
        Button Label
      </button>
    </div>

  </div>
</template>

<script>
import Button from '../../components/Button.vue'
import Description from '../../descriptions/Description'
import Collapser from '../../components/Collapser.vue'

let usage = `
<Button big>Big</Button>&nbsp;
<Button icon="add">Left Icon</Button>&nbsp;
<Button icon-right="expand_more">Right Icon</Button>&nbsp;
<Button alt>Alt</Button>&nbsp;
<Button icon="add" alt>Alt icon</Button>&nbsp;
<Button plain>Plain </Button>&nbsp;
<Button disabled>Disabled</Button>&nbsp;
<Button icon="menu" big plain></Button>&nbsp;
<Button icon="menu" big></Button>&nbsp;
<Button icon="menu" plain></Button>&nbsp;
<Button icon="menu"></Button>&nbsp;
<!-- OR -->
<button class="button primary">
  Button Label
</button>
`.slice(1)

export default {
  name: 'ButtonDemo',
  components: {Button, Description, Collapser},
  data: () => ({
    openUsage: true,
    usage
  }),
}
</script>
