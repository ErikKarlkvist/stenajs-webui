# Filter Package

The filter package provides components and utilities for implementing search filters in your application. It includes a drawer-based filter interface with support for various filter types and chip-based filter display.

## Components

### SearchFilterDrawer

A drawer component that displays the filter interface.

#### Props

```typescript
interface SearchFilterDrawerProps
  extends Omit<DrawerProps, "isOpen" | "onRequestClose"> {
  header?: string;
  headerContentRight?: ReactNode;
}
```

#### Example Usage

```tsx
import { SearchFilterDrawer } from "@stenajs-webui/filter";

const FilterDrawer = () => {
  return (
    <SearchFilterDrawer header="Filter Users">
      <SearchFilterSection title="Status">
        <FilterCheckboxList
          options={[
            { value: "active", label: "Active" },
            { value: "inactive", label: "Inactive" },
          ]}
        />
      </SearchFilterSection>
      <SearchFilterSection title="Date Range">
        <DateRangeCalendarSection />
      </SearchFilterSection>
    </SearchFilterDrawer>
  );
};
```

### SearchFilterButton

A button component that opens the filter drawer.

#### Props

```typescript
interface SearchFilterDrawerButtonProps {
  label?: string; // Default: "Filters"
  leftIcon?: IconDefinition; // Default: stenaSlidersMini
}
```

#### Example Usage

```tsx
import { SearchFilterButton } from "@stenajs-webui/filter";

const FilterButton = () => {
  return <SearchFilterButton label="Filter Users" />;
};
```

### SearchFilterSection

A section component for organizing filter groups.

#### Props

```typescript
interface SearchFilterSectionProps {
  title: string;
  children: ReactNode;
}
```

#### Example Usage

```tsx
import { SearchFilterSection } from "@stenajs-webui/filter";

const StatusFilter = () => {
  return (
    <SearchFilterSection title="Status">
      <FilterCheckboxList
        options={[
          { value: "active", label: "Active" },
          { value: "inactive", label: "Inactive" },
        ]}
      />
    </SearchFilterSection>
  );
};
```

### SearchFilterChips

A component that displays active filters as chips.

#### Props

```typescript
interface SearchFilterChipsProps {
  sections: Array<{
    title: string;
    chips: Array<SearchFilterSectionChipModel>;
    onClickRemoveOnChip: SearchFilterSectionOnClickRemoveOnChip<any>;
  }>;
}
```

#### Example Usage

```tsx
import { SearchFilterChips } from "@stenajs-webui/filter";

const ActiveFilters = () => {
  return (
    <SearchFilterChips
      sections={[
        {
          title: "Status",
          chips: [
            { value: "active", label: "Active" },
            { value: "inactive", label: "Inactive" },
          ],
          onClickRemoveOnChip: ({ value, setFormModelFields }) => {
            setFormModelFields({ status: undefined });
          },
        },
      ]}
    />
  );
};
```

## Filter Types

### Checkbox Filters

```tsx
import { FilterCheckboxList } from "@stenajs-webui/filter";

const StatusFilter = () => {
  return (
    <FilterCheckboxList
      options={[
        { value: "active", label: "Active" },
        { value: "inactive", label: "Inactive" },
      ]}
    />
  );
};
```

### Date Range Filters

```tsx
import { DateRangeCalendarSection } from "@stenajs-webui/filter";

const DateFilter = () => {
  return <DateRangeCalendarSection />;
};
```

### Chip Multi-Select Filters

```tsx
import { ChipMultiSelectSection } from "@stenajs-webui/filter";

const TagFilter = () => {
  return (
    <ChipMultiSelectSection
      options={[
        { value: "urgent", label: "Urgent" },
        { value: "important", label: "Important" },
      ]}
    />
  );
};
```

## Context and State Management

### SearchFilterContext

Provides the filter state and actions to child components.

```tsx
import { SearchFilterProvider } from "@stenajs-webui/filter";

const FilterApp = () => {
  return (
    <SearchFilterProvider>
      <SearchFilterButton />
      <SearchFilterDrawer>
        <SearchFilterSection title="Filters">
          {/* Filter components */}
        </SearchFilterSection>
      </SearchFilterDrawer>
    </SearchFilterProvider>
  );
};
```

### Local State Management

```tsx
import { useLocalSearchFilterState } from "@stenajs-webui/filter";

const FilterComponent = () => {
  const { state, dispatch } = useLocalSearchFilterState();
  // Use state and dispatch
};
```

## Best Practices

1. Organize filters into logical sections
2. Use appropriate filter types for different data
3. Implement proper state management
4. Handle filter removal gracefully
5. Consider mobile responsiveness
6. Use clear and descriptive labels
7. Implement proper keyboard navigation
8. Consider performance with large datasets
9. Use appropriate chip display for active filters
10. Implement proper error handling

## Accessibility

- All components support keyboard navigation
- ARIA attributes are included where appropriate
- Focus management is handled properly
- Filter states are clearly indicated
- Screen reader support is implemented

## Styling

Components can be styled using:

- CSS modules
- Theme variables
- Inline styles
- Custom class names

## Integration Example

```tsx
import {
  SearchFilterProvider,
  SearchFilterButton,
  SearchFilterDrawer,
  SearchFilterSection,
  FilterCheckboxList,
  DateRangeCalendarSection,
  SearchFilterChips,
} from "@stenajs-webui/filter";

const UserFilter = () => {
  return (
    <SearchFilterProvider>
      <div>
        <SearchFilterButton label="Filter Users" />
        <SearchFilterChips
          sections={[
            {
              title: "Status",
              chips: [
                { value: "active", label: "Active" },
                { value: "inactive", label: "Inactive" },
              ],
              onClickRemoveOnChip: ({ value, setFormModelFields }) => {
                setFormModelFields({ status: undefined });
              },
            },
          ]}
        />
      </div>
      <SearchFilterDrawer header="Filter Users">
        <SearchFilterSection title="Status">
          <FilterCheckboxList
            options={[
              { value: "active", label: "Active" },
              { value: "inactive", label: "Inactive" },
            ]}
          />
        </SearchFilterSection>
        <SearchFilterSection title="Date Range">
          <DateRangeCalendarSection />
        </SearchFilterSection>
      </SearchFilterDrawer>
    </SearchFilterProvider>
  );
};
```
