# Tooltip

## Overview
The tooltip package provides components for displaying contextual information when hovering over elements. It includes both simple tooltips and more complex popovers with additional functionality.

## Components

### Tooltip
Basic tooltip component that displays information on hover.

```tsx
import { Tooltip } from "@stenajs-webui/tooltip";
```

#### Props
| Prop | Type | Description |
|------|------|-------------|
| label | string | The text content of the tooltip |
| placement | Placement | Position of the tooltip relative to the trigger element |
| visible | boolean | Controls the visibility of the tooltip |
| variant | "info" \| "warning" \| "error" | Visual variant of the tooltip |
| maxWidth | CSSProperties["maxWidth"] | Maximum width of the tooltip |
| appendTo | HTMLElement \| null \| React.MutableRefObject<HTMLElement \| null> | Element to append the tooltip to |
| zIndex | number | z-index of the tooltip |
| children | ReactNode | The element that triggers the tooltip |

#### Placement Options
| Value | Description |
|-------|-------------|
| top | Above the trigger element |
| top-start | Above and aligned to the start of the trigger element |
| top-end | Above and aligned to the end of the trigger element |
| bottom | Below the trigger element |
| bottom-start | Below and aligned to the start of the trigger element |
| bottom-end | Below and aligned to the end of the trigger element |
| left | To the left of the trigger element |
| left-start | To the left and aligned to the start of the trigger element |
| left-end | To the left and aligned to the end of the trigger element |
| right | To the right of the trigger element |
| right-start | To the right and aligned to the start of the trigger element |
| right-end | To the right and aligned to the end of the trigger element |

#### Examples
```tsx
// Basic tooltip
<Tooltip label="This is a tooltip">
  <button>Hover me</button>
</Tooltip>

// Tooltip with variant
<Tooltip label="This is a warning" variant="warning">
  <button>Warning</button>
</Tooltip>

// Tooltip with custom placement
<Tooltip label="This tooltip appears on the right" placement="right">
  <button>Right-aligned</button>
</Tooltip>
```

### Popover
More complex popover component that can contain any content.

```tsx
import { Popover } from "@stenajs-webui/tooltip";
```

#### Props
| Prop | Type | Description |
|------|------|-------------|
| isOpen | boolean | Controls the visibility of the popover |
| onClose | () => void | Callback when popover closes |
| placement | Placement | Position of the popover relative to the trigger element |
| appendTo | HTMLElement \| null \| React.MutableRefObject<HTMLElement \| null> | Element to append the popover to |
| zIndex | number | z-index of the popover |
| children | ReactNode | The content of the popover |
| trigger | ReactNode | The element that triggers the popover |

#### Examples
```tsx
// Basic popover
<Popover
  trigger={<button>Click me</button>}
  isOpen={isOpen}
  onClose={() => setIsOpen(false)}
>
  <div>Popover content</div>
</Popover>

// Popover with custom placement
<Popover
  trigger={<button>Click me</button>}
  isOpen={isOpen}
  onClose={() => setIsOpen(false)}
  placement="right"
>
  <div>Popover content</div>
</Popover>
```

### ActionPrompt
Specialized popover for displaying action prompts.

```tsx
import { ActionPrompt } from "@stenajs-webui/tooltip";
```

#### Props
| Prop | Type | Description |
|------|------|-------------|
| isOpen | boolean | Controls the visibility of the prompt |
| onClose | () => void | Callback when prompt closes |
| onConfirm | () => void | Callback when action is confirmed |
| title | string | Title of the prompt |
| confirmLabel | string | Label for the confirm button |
| cancelLabel | string | Label for the cancel button |
| variant | "info" \| "warning" \| "error" | Visual variant of the prompt |

#### Examples
```tsx
<ActionPrompt
  isOpen={isOpen}
  onClose={() => setIsOpen(false)}
  onConfirm={handleConfirm}
  title="Are you sure?"
  confirmLabel="Yes"
  cancelLabel="No"
  variant="warning"
/>
```

## Best Practices

1. Use tooltips for short, contextual information
2. Use popovers for more complex content or interactions
3. Keep tooltip text concise and clear
4. Use appropriate variants for different types of information
5. Consider mobile users when choosing placement
6. Ensure tooltips are accessible with keyboard navigation
7. Use appropriate z-index values to prevent overlap issues

## Accessibility

The tooltip components are built with accessibility in mind:
- Keyboard navigation support
- ARIA attributes
- Focus management
- Screen reader compatibility
- Color contrast compliance

## Styling

Tooltips and popovers can be styled using CSS modules. The package provides default styles that can be overridden:

```css
/* Custom tooltip styles */
.myTooltip {
  background-color: var(--swui-primary-action-color);
  color: white;
}

/* Custom popover styles */
.myPopover {
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}
```

## Integration with Other Components

Tooltips can be used with any React component:

```tsx
import { Button } from "@stenajs-webui/elements";
import { Tooltip } from "@stenajs-webui/tooltip";

<Tooltip label="Click to save">
  <Button>Save</Button>
</Tooltip>
``` 