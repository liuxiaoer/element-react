<script>
  export default {
    data() {
      return {
        active: 0
      };
    },

    methods: {
      next() {
        if (this.active++ > 2) this.active = 0;
      }
    }
  }
</script>

## Steps 

Step-by-step guide to guide the user to complete the task in accordance with the process. Its steps can be set according to the actual application scenario and the number of the steps can't be less than 2.

### How to use

Simple step bar.

:::demo Set `active` attribute with `Number` type, which indicates the index of steps and starts from 0. You can set `space` attribute when the width of the step needs to be fixed which accepts `Boolean` type. The unit of the `space` attribute is `px`. If not set, it is adaptive. Setting the `finish-status` attribute can change the state of the steps that have been completed.

```html
<el-steps :space="100" :active="active" finish-status="success">
  <el-step title="Step 1"></el-step>
  <el-step title="Step 2"></el-step>
  <el-step title="Step 3"></el-step>
</el-steps>

<el-button style="margin-top: 12px;" @click.native="next">Next step</el-button>

<script>
  export default {
    data() {
      return {
        active: 0
      };
    },

    methods: {
      next() {
        if (this.active++ > 2) this.active = 0;
      }
    }
  }
</script>
```
:::

### Step bar that contains status

Shows the status of the step for each step.

:::demo Use `title` attribute to set the name of the step, or override the attribute setting with `slot`. We have list all the slot name for you at the end of the document.

```html
<el-steps :space="100" :active="1" finish-status="success">
  <el-step title="Done"></el-step>
  <el-step title="Processing"></el-step>
  <el-step title="Step 3"></el-step>
</el-steps>
```
:::

### Step bar with description

There is description for each step.

:::demo
```html
<el-steps :space="200" :active="1">
  <el-step title="Step 1" description="description"></el-step>
  <el-step title="Step 2" description="description"></el-step>
  <el-step title="Step 3" description="description"></el-step>
</el-steps>
```
:::

### Step bar with icon


A variety of custom icons can be used in the step bar.

:::demo The icon is set by the `icon` property, The types of icons can be found in the document for the Icon component, in addition, you can customize the icon through the slot name.

```html
<el-steps :space="100" :active="1">
  <el-step title="Step 1" icon="edit"></el-step>
  <el-step title="Step 2" icon="upload"></el-step>
  <el-step title="Step 3" icon="picture"></el-step>
</el-steps>
```
:::

### Vertical step bar

Vertical step bars.

:::demo You only need to set the `direction` attribute to` vertical` in the `el-steps` element.

```html
<el-steps :space="100" direction="vertical" :active="1">
  <el-step title="Step 1"></el-step>
  <el-step title="Step 2"></el-step>
  <el-step title="Step 3"></el-step>
</el-steps>
```
:::

### Steps Attributes

| Attribute      | Description    | Type      | Options       | Default   |
|---------- |-------- |---------- |-------------  |-------- |
| space | The spacing of each step, will be adaptive spacing if not set | Number | — | — |
| direction | display direction | string | vertical/horizontal | horizontal |
| active | Sets the current activation step  | number | — | 0 |
| process-status | Sets the status of current step | string | wait/process/finish/error/success | process |
| finish-status | Sets the status of end step | string | wait/process/finish/error/success | finish |

### Step Attributes
| Attribute      | Description    | Type      | Options       | Default   |
|---------- |-------- |---------- |-------------  |-------- |
| title | Title | string | — | — |
| description | Description | string | — | — |
| icon | Icon| Icons provided by Element Icon, can be written through the slot if you want to use <br> custom icon| string | — |

### Step Slot
| name | Description  |
|----|----|
| icon | Icon |
| title | Title |
| description | Description |
