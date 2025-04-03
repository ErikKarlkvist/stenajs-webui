# Input Mask Package Documentation

The input-mask package provides components and utilities for applying input masks to text inputs. It supports various mask patterns and allows for custom mask creation.

## Components

### MaskedTextInput

A text input component that applies a mask to the input value.

#### Props

- `mask: InputMask | InputMaskProvider` - The mask to apply
- `pipe?: InputMaskPipe` - Optional pipe function to transform the masked value
- `guide?: boolean` - Whether to show the mask guide (default: false)
- `keepCharPositions?: boolean` - Whether to keep character positions when deleting (default: false)
- `placeholderChar?: string` - Character to use as placeholder (default: " ")
- `showMask?: boolean` - Whether to show the mask (default: true)
- `value: string` - The input value
- `onValueChange: (value: string) => void` - Callback when value changes
- `onChange?: (event: ChangeEvent<HTMLInputElement>) => void` - Optional change event handler

#### Example Usage

```tsx
const [value, setValue] = useState("");

<MaskedTextInput
  mask={InputMasks.CREDIT_CARD}
  value={value}
  onValueChange={setValue}
  placeholder="Enter credit card number"
  guide
/>
```

## Hooks

### UseInputMask

A hook for applying input masks to any input element.

#### Parameters

- `inputRef: RefObject<HTMLInputElement>` - Reference to the input element
- `onChange?: (event: ChangeEvent<HTMLInputElement>) => void` - Optional change event handler
- `onValueChange?: (value: string) => void` - Optional value change handler
- `mask: InputMask | InputMaskProvider` - The mask to apply
- `pipe?: InputMaskPipe` - Optional pipe function
- `initialValue?: string` - Initial value
- `guide?: boolean` - Whether to show the mask guide
- `keepCharPositions?: boolean` - Whether to keep character positions
- `placeholderChar?: string` - Placeholder character
- `showMask?: boolean` - Whether to show the mask
- `enabled?: boolean` - Whether the mask is enabled

#### Example Usage

```tsx
const inputRef = useRef<HTMLInputElement>(null);
const [value, setValue] = useState("");

const { onChange } = useInputMask(
  inputRef,
  undefined,
  setValue,
  InputMasks.TIME,
  undefined,
  value,
  true
);

<input
  ref={inputRef}
  onChange={onChange}
  value={value}
  placeholder="Enter time"
/>
```

## Built-in Masks

### Credit Card

```tsx
InputMasks.CREDIT_CARD
// Format: XXXX XXXX XXXX XXXX
```

### Time

```tsx
InputMasks.TIME
// Format: HH:MM
```

### ISO Date

```tsx
InputMasks.ISO_DATE
// Format: YYYY-MM-DD
```

## Creating Custom Masks

### Using Array Syntax

```tsx
const phoneMask = [
  "(",
  /\d/,
  /\d/,
  /\d/,
  ")",
  " ",
  /\d/,
  /\d/,
  /\d/,
  "-",
  /\d/,
  /\d/,
  /\d/,
  /\d/,
];
// Format: (XXX) XXX-XXXX
```

### Using String Syntax

```tsx
const ssnMask = "XXX-XX-XXXX";
// Format: XXX-XX-XXXX
```

## Mask Pipes

Pipes allow you to transform the masked value before it's displayed.

### Example Pipe

```tsx
const uppercasePipe = (value: string) => value.toUpperCase();

<MaskedTextInput
  mask={[/[A-Za-z]/, /[A-Za-z]/, /[A-Za-z]/]}
  pipe={uppercasePipe}
  value={value}
  onValueChange={setValue}
/>
```

## Best Practices

1. Use appropriate masks for different input types
2. Consider using guide mode for complex masks
3. Implement proper validation alongside masks
4. Handle edge cases in custom pipes
5. Consider accessibility when using masks
6. Test mask behavior with different input methods
7. Use appropriate placeholder characters
8. Consider mobile input patterns

## Accessibility

- All components support keyboard navigation
- ARIA attributes are included where appropriate
- Focus management is handled properly
- Placeholder text is clear and descriptive
- Mask patterns are consistent and predictable

## Styling

Components can be styled using:
- CSS modules
- Theme variables
- Inline styles
- Custom class names

## Integration

Components can be used with other form components:

```tsx
<Form>
  <LabelledTextInput
    label="Credit Card"
    value={cardNumber}
    onValueChange={setCardNumber}
    component={MaskedTextInput}
    componentProps={{
      mask: InputMasks.CREDIT_CARD,
      guide: true,
    }}
  />
  <LabelledTextInput
    label="Expiration Date"
    value={expDate}
    onValueChange={setExpDate}
    component={MaskedTextInput}
    componentProps={{
      mask: [/[01]/, /\d/, "/", /\d/, /\d/],
      placeholder: "MM/YY",
    }}
  />
</Form>
``` 