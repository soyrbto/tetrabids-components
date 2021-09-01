<script>
  import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
  import Button from './Button.svelte';
</script>

<Meta
  title="Tetrabids/Button"
  component={Button}
  argTypes={{
    label: { control: 'text' },
    primary: { control: 'boolean' },
    color: {
      control: {
        type: 'select',
        options: ['orange', 'purple', 'white', 'blue'],
      },
    },
    onClick: { action: 'onClick' },
  }}
/>

<Template let:args>
  <Button {...args} on:click={args.onClick} />
</Template>

<Story
  name="Default"
  args={{
    primary: true,
    label: 'Button',
  }}
/>

<Story
  name="Default purple"
  args={{
    color: 'purple',
    label: 'Button',
  }}
/>

<Story
  name="Outline purple"
  args={{
    primary: false,
    color: 'purple',
    label: 'Button',
  }}
/>

<Story
  name="Outline orange"
  args={{
    primary: false,
    label: 'Button',
  }}
/>
