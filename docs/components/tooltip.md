# ToolTip

**KTooltip** is a tooltip component that is used when you need a simple label to be displayed when hovering over an element. KTooltip has a single slot that takes in the element that you want the tooltip to trigger over. At least the label prop must be passed in for the tooltip to display anything. For example a button:

<KTooltip label="Video Games">
  <KButton>&nbsp;🎮</KButton>
</KTooltip>

```vue
<KTooltip label="Video Games">
  <KButton>&nbsp;🎮</KButton>
</KTooltip>
```

## Props

### label

Here you can pass in the text to display in the toolip.

- `I am a new sample label`

<KTooltip label="I am a new sample label">
  <KButton>Sample Button</KButton>
</KTooltip>

```vue
<KTooltip label="I am a new sample label">
  <KButton>Sample Button</KButton>
</KTooltip>
```

### position

This is where the tooltip will appear - by default it appears on top.
Here are the different options:

- `top`
- `bottom`
- `left`
- `right`

<div class="d-flex justify-content-around">
  <KTooltip placement="bottom" label="A label that appears on the bottom">
    <KButton>bottom</KButton>
  </KTooltip>
  <KTooltip placement="top" label="A label that appears on the top">
    <KButton>top</KButton>
  </KTooltip>
  <KTooltip placement="left" label="A label that appears on the left">
    <KButton>left</KButton>
  </KTooltip>
  <KTooltip placement="right" label="A label that appears on the right">
    <KButton>right</KButton>
  </KTooltip>
</div>

```vue
<KTooltip position="bottom" label="A label that appears on the bottom">
  <KButton>Sample Button</KButton>
</KTooltip>
```

### positionFixed

Use fixed positioning of the popover to avoid content being clipped by parental boundaries - defaults to `false`. See [`KPop` docs](popover.html#positionfixed) for more information.

## Slots

- `Default` There is a main slot that takes in the element you want the popover to be triggered over.

```vue
<KTooltip label="a cool label">
  <!-- Your element goes here -->
  <KButton>button</KButton>
</KTooltip>
```

- `Content` This allows you to slot in any html content

<KTooltip label="Video Games">
  <KButton>&nbsp;✌🏻</KButton>
  <template v-slot:content>
    <span><b>yoyo</b> <span class="color-red-500">kooltip</span></span>
  </template>
</KTooltip>

```vue
<KTooltip>
  <KButton>&nbsp;✌🏻</KButton>
  <template v-slot:content>
    <span><b>yoyo</b> <span class="color-red-500">kooltip</span></span>
  </template>
</KTooltip>
```

## Theming

| Variable | Purpose
|:-------- |:-------
| `--KTooltipBackground`| Background color
| `--KTooltipColor`| Color of text

Example:

<KTooltip class="tooltip-blue" label="Video Games">
  <KButton>themed tooltip</KButton>
</KTooltip>

```vue
<template>
  <KTooltip class="tooltip-blue" label="Video Games">
    <KButton class="primary">themed tooltip</KButton>
  </KTooltip>
</template>

<style>
.tooltip-blue {
  --KTooltipBackground: var(--blue-300);
  --KTooltipColor: var(--blue-500);
}
</style>
```

<style>
.tooltip-blue {
  --KTooltipBackground: var(--blue-500);
  --KTooltipColor: var(--blue-200);
}
</style>