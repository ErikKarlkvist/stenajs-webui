# Select

## Overview

The select package provides a comprehensive set of select components for React applications, built on top of react-select. It includes various types of select components for different use cases, from simple single-select to complex grouped multi-select.

## Components

### Select

Basic single-select component.

```tsx
import { Select } from "@stenajs-webui/select";
```

#### Props

| Prop        | Type                                              | Description                              |
| ----------- | ------------------------------------------------- | ---------------------------------------- |
| options     | Array<{ label: string; value: string }>           | List of selectable options               |
| value       | { label: string; value: string }                  | Currently selected value                 |
| onChange    | (value: { label: string; value: string }) => void | Callback when selection changes          |
| variant     | "standard" \| "light"                             | Visual variant of the select             |
| isClearable | boolean                                           | Whether the select can be cleared        |
| isDisabled  | boolean                                           | Whether the select is disabled           |
| placeholder | string                                            | Placeholder text                         |
| styles      | object                                            | Custom styles to override default styles |

#### Example

```tsx
<Select
  options={[
    { value: "1", label: "Option 1" },
    { value: "2", label: "Option 2" },
  ]}
  value={selectedOption}
  onChange={handleChange}
  placeholder="Select an option"
/>
```

### MultiSelect

Multi-select component that allows selecting multiple values.

```tsx
import { MultiSelect } from "@stenajs-webui/select";
```

#### Props

| Prop        | Type                                                     | Description                              |
| ----------- | -------------------------------------------------------- | ---------------------------------------- |
| options     | Array<{ label: string; value: string }>                  | List of selectable options               |
| value       | Array<{ label: string; value: string }>                  | Currently selected values                |
| onChange    | (value: Array<{ label: string; value: string }>) => void | Callback when selection changes          |
| variant     | "standard" \| "light"                                    | Visual variant of the select             |
| isClearable | boolean                                                  | Whether the select can be cleared        |
| isDisabled  | boolean                                                  | Whether the select is disabled           |
| placeholder | string                                                   | Placeholder text                         |
| styles      | object                                                   | Custom styles to override default styles |

#### Example

```tsx
<MultiSelect
  options={[
    { value: "1", label: "Option 1" },
    { value: "2", label: "Option 2" },
  ]}
  value={selectedOptions}
  onChange={handleChange}
  placeholder="Select options"
/>
```

### AsyncSelect

Select component that loads options asynchronously.

```tsx
import { AsyncSelect } from "@stenajs-webui/select";
```

#### Props

| Prop           | Type                                                                     | Description                               |
| -------------- | ------------------------------------------------------------------------ | ----------------------------------------- |
| loadOptions    | (inputValue: string) => Promise<Array<{ label: string; value: string }>> | Function to load options                  |
| defaultOptions | boolean \| Array<{ label: string; value: string }>                       | Default options to show before user input |
| cacheOptions   | boolean                                                                  | Whether to cache loaded options           |
| value          | { label: string; value: string }                                         | Currently selected value                  |
| onChange       | (value: { label: string; value: string }) => void                        | Callback when selection changes           |
| variant        | "standard" \| "light"                                                    | Visual variant of the select              |

#### Example

```tsx
<AsyncSelect
  loadOptions={async (inputValue) => {
    const response = await fetch(`/api/options?search=${inputValue}`);
    return response.json();
  }}
  value={selectedOption}
  onChange={handleChange}
  placeholder="Search and select"
/>
```

### AsyncMultiSelect

Multi-select component that loads options asynchronously.

```tsx
import { AsyncMultiSelect } from "@stenajs-webui/select";
```

#### Props

| Prop           | Type                                                                     | Description                               |
| -------------- | ------------------------------------------------------------------------ | ----------------------------------------- |
| loadOptions    | (inputValue: string) => Promise<Array<{ label: string; value: string }>> | Function to load options                  |
| defaultOptions | boolean \| Array<{ label: string; value: string }>                       | Default options to show before user input |
| cacheOptions   | boolean                                                                  | Whether to cache loaded options           |
| value          | Array<{ label: string; value: string }>                                  | Currently selected values                 |
| onChange       | (value: Array<{ label: string; value: string }>) => void                 | Callback when selection changes           |
| variant        | "standard" \| "light"                                                    | Visual variant of the select              |

#### Example

```tsx
<AsyncMultiSelect
  loadOptions={async (inputValue) => {
    const response = await fetch(`/api/options?search=${inputValue}`);
    return response.json();
  }}
  value={selectedOptions}
  onChange={handleChange}
  placeholder="Search and select options"
/>
```

### CreatableSelect

Select component that allows creating new options.

```tsx
import { CreatableSelect } from "@stenajs-webui/select";
```

#### Props

| Prop           | Type                                              | Description                           |
| -------------- | ------------------------------------------------- | ------------------------------------- |
| options        | Array<{ label: string; value: string }>           | List of selectable options            |
| value          | { label: string; value: string }                  | Currently selected value              |
| onChange       | (value: { label: string; value: string }) => void | Callback when selection changes       |
| onCreateOption | (inputValue: string) => void                      | Callback when a new option is created |
| variant        | "standard" \| "light"                             | Visual variant of the select          |
| ariaLabelClear | string                                            | ARIA label for the clear button       |

#### Example

```tsx
<CreatableSelect
  options={[
    { value: "1", label: "Option 1" },
    { value: "2", label: "Option 2" },
  ]}
  value={selectedOption}
  onChange={handleChange}
  onCreateOption={handleCreate}
  placeholder="Select or create an option"
/>
```

### GroupedMultiSelect

Multi-select component that supports grouped options.

```tsx
import { GroupedMultiSelect } from "@stenajs-webui/select";
```

#### Props

| Prop             | Type                                                                                      | Description                     |
| ---------------- | ----------------------------------------------------------------------------------------- | ------------------------------- |
| options          | Array<{ label: string; options: Array<{ label: string; value: string }> }>                | Grouped options                 |
| value            | Array<{ label: string; value: string }>                                                   | Currently selected values       |
| onChange         | (value: Array<{ label: string; value: string }>) => void                                  | Callback when selection changes |
| variant          | "standard" \| "light"                                                                     | Visual variant of the select    |
| formatGroupLabel | (group: { label: string; options: Array<{ label: string; value: string }> }) => ReactNode | Custom group label formatter    |

#### Example

```tsx
<GroupedMultiSelect
  options={[
    {
      label: "Group 1",
      options: [
        { value: "1", label: "Option 1" },
        { value: "2", label: "Option 2" },
      ],
    },
    {
      label: "Group 2",
      options: [
        { value: "3", label: "Option 3" },
        { value: "4", label: "Option 4" },
      ],
    },
  ]}
  value={selectedOptions}
  onChange={handleChange}
  placeholder="Select options"
/>
```

### OverflowingMultiSelect

Multi-select component that shows only the first selected value and a count of remaining selections.

```tsx
import { OverflowingMultiSelect } from "@stenajs-webui/select";
```

#### Props

| Prop     | Type                                                     | Description                     |
| -------- | -------------------------------------------------------- | ------------------------------- |
| options  | Array<{ label: string; value: string }>                  | List of selectable options      |
| value    | Array<{ label: string; value: string }>                  | Currently selected values       |
| onChange | (value: Array<{ label: string; value: string }>) => void | Callback when selection changes |
| variant  | "standard" \| "light"                                    | Visual variant of the select    |

#### Example

```tsx
<OverflowingMultiSelect
  options={[
    { value: "1", label: "Option 1" },
    { value: "2", label: "Option 2" },
    { value: "3", label: "Option 3" },
  ]}
  value={selectedOptions}
  onChange={handleChange}
  placeholder="Select options"
/>
```

## Common Features

All select components share these common features:

- Keyboard navigation
- Search/filter functionality
- Customizable styling
- Clear button
- Placeholder text
- Disabled state
- Loading state
- Error state
- Custom option rendering
- Custom value rendering
- Custom menu rendering
- Custom indicators
- Custom input rendering

## Styling

Components can be styled using the `styles` prop, which accepts an object of style overrides. The styling follows the react-select styling API.

```tsx
const customStyles = {
  control: (base) => ({
    ...base,
    backgroundColor: "#f5f5f5",
  }),
  option: (base, state) => ({
    ...base,
    backgroundColor: state.isSelected ? "#007bff" : "white",
    color: state.isSelected ? "white" : "black",
  }),
};

<Select
  styles={customStyles}
  // ... other props
/>;
```

## Variants

All components support two visual variants:

- `standard`: Default styling with a border
- `light`: Lighter styling with minimal visual elements

## Accessibility

All components are built with accessibility in mind:

- ARIA labels and roles
- Keyboard navigation
- Screen reader support
- Focus management
- Color contrast compliance
