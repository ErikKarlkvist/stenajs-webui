# Forms Package Documentation

The forms package provides a comprehensive set of form components and utilities for building user interfaces. It includes input components, selection components, and hooks for form handling.

## Input Components

### TextInput

A versatile text input component with various styling options and features.

#### Props

- `value: string` - The input value
- `onValueChange: (value: string) => void` - Callback when value changes
- `variant?: "standard" | "loading" | "warning" | "error" | "modified" | "success"` - Visual variant
- `disabled?: boolean` - Whether the input is disabled
- `placeholder?: string` - Placeholder text
- `iconLeft?: IconDefinition` - Left icon
- `iconRight?: IconDefinition` - Right icon
- `contentLeft?: ReactNode` - Left content
- `contentRight?: ReactNode` - Right content
- `buttonLeft?: ReactNode` - Left button
- `buttonRight?: ReactNode` - Right button
- `selectAllOnMount?: boolean` - Whether to select all text on mount
- `moveCursorToEndOnMount?: boolean` - Whether to move cursor to end on mount
- `autoFocus?: boolean` - Whether to auto-focus the input
- `onDone?: (value: string) => void` - Callback when done editing
- `onEnter?: () => void` - Callback when Enter is pressed
- `onEsc?: () => void` - Callback when Escape is pressed
- `onMove?: (direction: MoveDirection) => void` - Callback when moving outside field
- `borderRadiusVariant?: "normalBorder" | "onlyTop" | "onlyBottom" | "onlyLeft" | "onlyRight"` - Border style
- `alwaysShowPlaceholder?: boolean` - Whether to always show placeholder

#### Example Usage

```tsx
const [value, setValue] = useState("");

<TextInput
  value={value}
  onValueChange={setValue}
  placeholder="Enter text"
  iconLeft={faSearch}
  variant="standard"
  onEnter={() => console.log("Enter pressed")}
/>
```

### TextArea

A multi-line text input component.

#### Props

- `value: string` - The input value
- `onValueChange: (value: string) => void` - Callback when value changes
- `disabled?: boolean` - Whether the input is disabled
- `placeholder?: string` - Placeholder text
- `rows?: number` - Number of visible rows
- `resize?: "none" | "both" | "horizontal" | "vertical"` - Resize behavior

#### Example Usage

```tsx
const [value, setValue] = useState("");

<TextArea
  value={value}
  onValueChange={setValue}
  placeholder="Enter description"
  rows={4}
  resize="vertical"
/>
```

### NumericTextInput

A text input component for numeric values.

#### Props

- `value: number | undefined` - The numeric value
- `onValueChange: (value: number | undefined) => void` - Callback when value changes
- `min?: number` - Minimum value
- `max?: number` - Maximum value
- `step?: number` - Step value
- `disabled?: boolean` - Whether the input is disabled
- `placeholder?: string` - Placeholder text

#### Example Usage

```tsx
const [value, setValue] = useState<number | undefined>(0);

<NumericTextInput
  value={value}
  onValueChange={setValue}
  min={0}
  max={100}
  step={1}
  placeholder="Enter number"
/>
```

### PasswordInput

A text input component for passwords.

#### Props

- `value: string` - The password value
- `onValueChange: (value: string) => void` - Callback when value changes
- `disabled?: boolean` - Whether the input is disabled
- `placeholder?: string` - Placeholder text
- `showPassword?: boolean` - Whether to show the password

#### Example Usage

```tsx
const [value, setValue] = useState("");
const [showPassword, setShowPassword] = useState(false);

<PasswordInput
  value={value}
  onValueChange={setValue}
  placeholder="Enter password"
  showPassword={showPassword}
/>
```

## Selection Components

### Checkbox

A checkbox component for boolean values.

#### Props

- `value: boolean` - The checkbox value
- `onValueChange: (value: boolean) => void` - Callback when value changes
- `indeterminate?: boolean` - Whether the checkbox is in indeterminate state
- `size?: "standard" | "small"` - Size variant
- `disabled?: boolean` - Whether the checkbox is disabled

#### Example Usage

```tsx
const [checked, setChecked] = useState(false);

<Checkbox
  value={checked}
  onValueChange={setChecked}
  indeterminate={false}
  size="standard"
/>
```

### RadioButton

A radio button component for single selection.

#### Props

- `value: boolean` - The radio button value
- `onValueChange: (value: boolean) => void` - Callback when value changes
- `disabled?: boolean` - Whether the radio button is disabled
- `label?: string` - Label text

#### Example Usage

```tsx
const [selected, setSelected] = useState(false);

<RadioButton
  value={selected}
  onValueChange={setSelected}
  label="Option 1"
/>
```

### Switch

A switch component for boolean values.

#### Props

- `value: boolean` - The switch value
- `onValueChange: (value: boolean) => void` - Callback when value changes
- `disabled?: boolean` - Whether the switch is disabled
- `label?: string` - Label text

#### Example Usage

```tsx
const [enabled, setEnabled] = useState(false);

<Switch
  value={enabled}
  onValueChange={setEnabled}
  label="Enable feature"
/>
```

## Label Components

### InputLabel

A label component for form inputs.

#### Props

- `label: string` - Label text
- `required?: boolean` - Whether the field is required
- `disabled?: boolean` - Whether the label is disabled
- `children?: ReactNode` - Input component

#### Example Usage

```tsx
<InputLabel label="Username" required>
  <TextInput value={value} onValueChange={setValue} />
</InputLabel>
```

### LabelledTextInput

A text input with an integrated label.

#### Props

- `label: string` - Label text
- `value: string` - The input value
- `onValueChange: (value: string) => void` - Callback when value changes
- `required?: boolean` - Whether the field is required
- `disabled?: boolean` - Whether the input is disabled
- `placeholder?: string` - Placeholder text

#### Example Usage

```tsx
const [value, setValue] = useState("");

<LabelledTextInput
  label="Email"
  value={value}
  onValueChange={setValue}
  required
  placeholder="Enter email"
/>
```

## Best Practices

1. Use appropriate input components based on data type
2. Implement proper validation and error handling
3. Use labels for all form inputs
4. Handle disabled states appropriately
5. Consider accessibility when implementing forms
6. Use consistent styling across form components
7. Implement proper keyboard navigation
8. Provide clear feedback for user actions

## Accessibility

- All components support keyboard navigation
- ARIA attributes are included for screen readers
- Focus management is handled properly
- Color contrast meets accessibility standards
- Labels are properly associated with inputs

## Styling

Components can be styled using:
- CSS modules
- Theme customization
- Inline styles
- Variant props

## Integration

Components can be used together to create complex forms:

```tsx
<Box spacing={2}>
  <Heading variant="h3">User Registration</Heading>
  <Column gap={2}>
    <LabelledTextInput
      label="Username"
      value={username}
      onValueChange={setUsername}
      required
      placeholder="Enter username"
    />
    <LabelledTextInput
      label="Email"
      value={email}
      onValueChange={setEmail}
      required
      placeholder="Enter email"
    />
    <PasswordInput
      value={password}
      onValueChange={setPassword}
      placeholder="Enter password"
    />
    <Row gap={2}>
      <Checkbox
        value={acceptTerms}
        onValueChange={setAcceptTerms}
        label="I accept the terms and conditions"
      />
    </Row>
    <Button
      label="Register"
      onClick={handleRegister}
      disabled={!acceptTerms}
    />
  </Column>
</Box>
``` 