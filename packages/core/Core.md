# Core Package Documentation

The core package provides fundamental UI components, layout utilities, and hooks that serve as the building blocks for the Stenajs WebUI library. It includes layout components, text components, hooks, and utility functions.

## Layout Components

### Box

A versatile layout component that serves as the foundation for other layout components.

#### Props

- `row?: boolean` - If true, children are placed in a row
- `spacing?: boolean | number` - Adds spacing over and under content
- `indent?: boolean | number` - Adds spacing left and right of content
- `gap?: boolean | number` - Adds spacing between children
- `columnGap?: boolean | number` - Adds gap between columns
- `rowGap?: boolean | number` - Adds gap between rows
- `shadow?: string | "box" | "popover" | "modal" | "bottom"` - Adds a shadow around the box
- `background?: string` - Sets the background of the box
- `border?: string` - Sets the border of the box
- `borderColor?: string` - Sets the border color of the box
- `hoverBackground?: string` - Sets the background on hover
- `hoverBorder?: string` - Sets the border on hover
- `focusBackground?: string` - Sets the background on focus
- `focusBorder?: string` - Sets the border on focus
- `focusWithinBackground?: string` - Sets the background when focus is within
- `focusWithinBorder?: string` - Sets the border when focus is within

#### Example Usage

```tsx
<Box
  spacing={2}
  indent={1}
  gap={1}
  shadow="box"
  background="var(--swui-background-color)"
  hoverBackground="var(--swui-hover-background-color)"
>
  <div>Content</div>
</Box>
```

### Column

A layout component that arranges children in a vertical column.

#### Props

Inherits all props from Box component.

#### Example Usage

```tsx
<Column gap={1}>
  <div>First item</div>
  <div>Second item</div>
  <div>Third item</div>
</Column>
```

### Row

A layout component that arranges children in a horizontal row.

#### Props

Inherits all props from Box component.

#### Example Usage

```tsx
<Row gap={1} justifyContent="space-between">
  <div>Left</div>
  <div>Right</div>
</Row>
```

### Indent

A component that adds horizontal spacing.

#### Props

- `num?: number` - Number of indent units (default: 1)

#### Example Usage

```tsx
<Row>
  <div>Content</div>
  <Indent num={2} />
  <div>More content</div>
</Row>
```

### Space

A component that adds vertical spacing.

#### Props

- `num?: number` - Number of space units (default: 1)

#### Example Usage

```tsx
<Column>
  <div>First item</div>
  <Space num={2} />
  <div>Second item</div>
</Column>
```

## Text Components

### Text

A versatile text component with various styling options.

#### Props

- `variant?: "standard" | "caption" | "overline" | "bold"` - Text variant
- `size?: "large" | "medium" | "small" | "smaller"` - Text size
- `userSelect?: string` - CSS user-select property
- `whiteSpace?: string` - CSS white-space property
- `wordBreak?: string` - CSS word-break property
- `textAlign?: string` - CSS text-align property
- `color?: string` - Text color

#### Example Usage

```tsx
<Text variant="bold" size="large" color="var(--swui-text-primary-color)">
  Bold Large Text
</Text>
```

### Heading

A component for displaying headings.

#### Props

- `variant?: "h1" | "h2" | "h3" | "h4" | "h5" | "h6"` - Heading level
- `color?: string` - Text color

#### Example Usage

```tsx
<Heading variant="h1">Main Title</Heading>
<Heading variant="h2">Section Title</Heading>
```

## Hooks

### UseBoolean

A hook for managing boolean state.

#### Example Usage

```tsx
const [isOpen, { toggle, setTrue, setFalse }] = useBoolean(false);
```

### UseDebounce

A hook for debouncing values.

#### Example Usage

```tsx
const debouncedValue = useDebounce(value, 300);
```

### UseOnClickOutside

A hook for detecting clicks outside an element.

#### Example Usage

```tsx
const ref = useOnClickOutside(() => {
  setIsOpen(false);
});
```

### UseElementDimensions

A hook for tracking element dimensions.

#### Example Usage

```tsx
const { width, height } = useElementDimensions(ref);
```

### UseMouseIsOver

A hook for tracking mouse hover state.

#### Example Usage

```tsx
const isHovered = useMouseIsOver(ref);
```

## Best Practices

1. Use Box as the foundation for custom components
2. Leverage Column and Row for layout organization
3. Use Indent and Space for consistent spacing
4. Utilize Text and Heading components for typography
5. Take advantage of hooks for common functionality
6. Follow the theme system for consistent styling

## Accessibility

- All components support keyboard navigation
- ARIA attributes are included where appropriate
- Focus management is handled properly
- Color contrast meets accessibility standards

## Styling

Components can be styled using:

- CSS modules
- Theme variables
- Inline styles
- Styled-system props

## Integration

Components can be used together to create complex layouts:

```tsx
<Box spacing={2}>
  <Heading variant="h1">Dashboard</Heading>
  <Row gap={2}>
    <Column flex={1}>
      <Text variant="bold">Statistics</Text>
      <Space />
      <Box background="var(--swui-background-color)" spacing={1}>
        <Text>Total Users: 1000</Text>
      </Box>
    </Column>
    <Column flex={1}>
      <Text variant="bold">Recent Activity</Text>
      <Space />
      <Box background="var(--swui-background-color)" spacing={1}>
        <Text>New user registered</Text>
      </Box>
    </Column>
  </Row>
</Box>
```
