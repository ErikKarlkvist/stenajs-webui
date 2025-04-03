# Calendar Package Documentation

The calendar package provides a comprehensive set of components for date selection and display. It includes various calendar types, input components, and utilities for date handling.

## Calendar Types

### DateRangeCalendar

A calendar component for selecting date ranges.

#### Props

- `value: DateRange` - The selected date range
- `onValueChange: (value: DateRange) => void` - Callback when date range changes
- `focusedInput?: "startDate" | "endDate"` - Which input is currently focused
- `setFocusedInput: (focusedInput: "startDate" | "endDate" | undefined) => void` - Callback to set focused input
- `initialDateInFocus?: Date` - Initial date to show in focus
- `minDate?: Date` - Minimum selectable date
- `maxDate?: Date` - Maximum selectable date
- `theme?: CalendarTheme` - Custom theme for the calendar

#### Example Usage

```tsx
const [dateRange, setDateRange] = useState<DateRange>({
  startDate: new Date(),
  endDate: new Date(),
});

<DateRangeCalendar
  value={dateRange}
  onValueChange={setDateRange}
  focusedInput="startDate"
  setFocusedInput={setFocusedInput}
  minDate={new Date(2020, 0, 1)}
  maxDate={new Date(2025, 11, 31)}
/>
```

### SingleDateCalendar

A calendar component for selecting a single date.

#### Props

- `value: Date | undefined` - The selected date
- `onChange: (value: Date | undefined) => void` - Callback when date changes
- `minDate?: Date` - Minimum selectable date
- `maxDate?: Date` - Maximum selectable date
- `theme?: CalendarTheme` - Custom theme for the calendar

#### Example Usage

```tsx
const [date, setDate] = useState<Date | undefined>(new Date());

<SingleDateCalendar
  value={date}
  onChange={setDate}
  minDate={new Date(2020, 0, 1)}
  maxDate={new Date(2025, 11, 31)}
/>
```

### MultiDateCalendar

A calendar component for selecting multiple dates.

#### Props

- `value: Date[]` - The selected dates
- `onChange: (value: Date[]) => void` - Callback when dates change
- `minDate?: Date` - Minimum selectable date
- `maxDate?: Date` - Maximum selectable date
- `theme?: CalendarTheme` - Custom theme for the calendar

#### Example Usage

```tsx
const [dates, setDates] = useState<Date[]>([]);

<MultiDateCalendar
  value={dates}
  onChange={setDates}
  minDate={new Date(2020, 0, 1)}
  maxDate={new Date(2025, 11, 31)}
/>
```

## Input Components

### DateRangeInput

An input component for selecting date ranges with a calendar popover.

#### Props

- `value: DateRange` - The selected date range
- `onValueChange: (value: DateRange) => void` - Callback when date range changes
- `displayFormat?: string` - Date format in input field (default: YYYY-MM-dd)
- `placeholderStartDate?: string` - Placeholder for start date (default: "Start date")
- `placeholderEndDate?: string` - Placeholder for end date (default: "End date")
- `width?: string` - Width of input element (default: "125px")
- `calendarTheme?: CalendarTheme` - Custom theme for the calendar
- `disabled?: boolean` - Disables the input and popover
- `portalTarget?: HTMLElement` - Portal target for popover
- `zIndex?: number` - Z-index for popover

#### Example Usage

```tsx
const [dateRange, setDateRange] = useState<DateRange>({
  startDate: new Date(),
  endDate: new Date(),
});

<DateRangeInput
  value={dateRange}
  onValueChange={setDateRange}
  displayFormat="MM/dd/yyyy"
  placeholderStartDate="From"
  placeholderEndDate="To"
  width="150px"
/>
```

### DateInput

An input component for selecting a single date with a calendar popover.

#### Props

- `value: Date | undefined` - The selected date
- `onValueChange: (value: Date | undefined) => void` - Callback when date changes
- `displayFormat?: string` - Date format in input field (default: YYYY-MM-dd)
- `placeholder?: string` - Placeholder text (default: "Select date")
- `width?: string` - Width of input element (default: "125px")
- `calendarTheme?: CalendarTheme` - Custom theme for the calendar
- `disabled?: boolean` - Disables the input and popover
- `portalTarget?: HTMLElement` - Portal target for popover
- `zIndex?: number` - Z-index for popover

#### Example Usage

```tsx
const [date, setDate] = useState<Date | undefined>(new Date());

<DateInput
  value={date}
  onValueChange={setDate}
  displayFormat="MM/dd/yyyy"
  placeholder="Choose date"
  width="150px"
/>
```

## Features

### MonthPicker

A component for selecting months.

#### Props

- `value: Date` - The selected month
- `onChange: (value: Date) => void` - Callback when month changes
- `minDate?: Date` - Minimum selectable month
- `maxDate?: Date` - Maximum selectable month

#### Example Usage

```tsx
const [month, setMonth] = useState<Date>(new Date());

<MonthPicker
  value={month}
  onChange={setMonth}
  minDate={new Date(2020, 0, 1)}
  maxDate={new Date(2025, 11, 31)}
/>
```

### YearPicker

A component for selecting years.

#### Props

- `value: Date` - The selected year
- `onChange: (value: Date) => void` - Callback when year changes
- `minDate?: Date` - Minimum selectable year
- `maxDate?: Date` - Maximum selectable year

#### Example Usage

```tsx
const [year, setYear] = useState<Date>(new Date());

<YearPicker
  value={year}
  onChange={setYear}
  minDate={new Date(2020, 0, 1)}
  maxDate={new Date(2025, 11, 31)}
/>
```

## Best Practices

1. Use appropriate calendar type based on selection needs
2. Set minDate and maxDate to prevent invalid selections
3. Use DateRangeInput for date range selection
4. Use DateInput for single date selection
5. Customize displayFormat to match your application's needs
6. Handle disabled states appropriately
7. Use portalTarget for proper popover positioning
8. Consider accessibility when implementing calendar components

## Accessibility

- All components support keyboard navigation
- ARIA attributes are included for screen readers
- Focus management is handled properly
- Color contrast meets accessibility standards

## Styling

Components can be styled using:
- CSS modules
- Theme customization
- Custom calendar themes

## Integration

Components can be used together to create complex date selection interfaces:

```tsx
<Box spacing={2}>
  <Heading variant="h3">Date Selection</Heading>
  <Row gap={2}>
    <Column>
      <Text variant="bold">Single Date</Text>
      <Space />
      <DateInput
        value={singleDate}
        onValueChange={setSingleDate}
        displayFormat="MM/dd/yyyy"
      />
    </Column>
    <Column>
      <Text variant="bold">Date Range</Text>
      <Space />
      <DateRangeInput
        value={dateRange}
        onValueChange={setDateRange}
        displayFormat="MM/dd/yyyy"
      />
    </Column>
  </Row>
</Box>
``` 