# Grid Package

The grid package provides a powerful and flexible table component (`StandardTable`) for displaying and managing tabular data. It supports features like sorting, filtering, row selection, column grouping, and sticky headers/columns.

## Components

### StandardTable

The main table component that provides a flexible and feature-rich grid implementation.

#### Props

```typescript
interface StandardTableProps<
  TItem extends object,
  TColumnKey extends string,
  TColumnGroupKey extends string,
> {
  variant?: StandardTableVariant; // 'relaxed' | 'standard' | 'condensed' | 'compact'
  tableId?: string;
  rowIndexOffset?: number;
  colIndexOffset?: number;
  config: StandardTableConfig<TItem, TColumnKey, TColumnGroupKey>;
  items?: Array<TItem>;
  error?: Error;
  loading?: boolean;
  noItemsContentRight?: ReactNode;
  noItemsContentBottom?: ReactNode;
  noItemsHeader?: string;
  noItemsLabel?: string;
  bannerError?: ResultListBannerState;
  errorLabel?: string;
  tableContext?: TableContext<TColumnKey>;
  columnOrder?: Array<TColumnKey>;
  columnGroupOrder?: Array<TColumnGroupKey>;
  onKeyDown?: StandardTableOnKeyDown<TItem, TColumnKey>;
  onSortOrderChange?: StandardTableOnSortOrderChange<TColumnKey>;
  renderExtraHeadRows?: () => ReactNode;
  renderExtraRowTop?: () => ReactNode;
  renderExtraRowBottom?: () => ReactNode;
}
```

## Configuration

### StandardTableConfig

The configuration object that defines the table's behavior and appearance.

#### Base Configuration

```typescript
interface StandardTableConfigBase<TItem, TColumnKey extends string> {
  disableSorting?: boolean;
  enableExternalSorting?: boolean;
  initialSortOrder?: TColumnKey;
  initialSortOrderDesc?: boolean;
  keyResolver: (item: TItem) => string;
  showHeaderExpandCollapse?: boolean;
  enableExpandCollapse?: boolean;
  expandCollapseDisableResolver?: (item: TItem) => boolean;
  renderRowExpansion?: (
    item: TItem,
    args: RowExpansionArgs,
  ) => ReactNode | undefined;
  disableInfiniteList?: boolean;
  rowBackgroundResolver?: (
    item: TItem,
    selected: boolean,
  ) => string | RowBackgroundResolverColorCombination | undefined;
  checkboxDisabledResolver?: (item: TItem) => boolean;
  enableGridCell?: boolean;
  gridCellOptions?: Omit<
    UseGridCellOptions<string>,
    | "colIndex"
    | "rowIndex"
    | "numRows"
    | "numCols"
    | "tableId"
    | "isEditable"
    | "onChange"
  >;
  showHeaderCheckbox?: boolean;
  showRowCheckbox?: boolean;
  rowIndent?: boolean | number;
  stickyHeader?: boolean;
  stickyCheckboxColumn?: boolean;
  zIndex?: number;
  infoIconTooltipAppendTo?: TooltipProps["appendTo"];
  infoIconTooltipZIndex?: number;
  headerRowOffsetTop?: string;
  sortOrderIconVariant?: SortOrderIconVariant;
  defaultCellRenderer?: DefaultStandardTableCellRenderer<TItem>;
  defaultTextSize?: TextSize;
}
```

### Column Configuration

#### StandardTableColumnConfig

```typescript
interface StandardTableColumnOptions<
  TItem,
  TItemValue,
  TColumnKey extends string,
> {
  columnLabel?: string;
  infoIconTooltipText?: string;
  minWidth?: string;
  width?: string;
  renderCell?: StandardTableCellRenderer<TItemValue, TItem>;
  background?: string;
  backgroundResolver?: BackgroundResolver<TItem>;
  borderLeft?: string | boolean;
  justifyContentHeader?: string;
  justifyContentCell?: string;
  itemLabelFormatter?: (value: TItemValue, item: TItem) => string;
  isEditable?: boolean | ((item: TItem) => boolean);
  onChange?: (item: TItem, value: string | undefined) => void;
  onKeyDown?: (
    ev: React.KeyboardEvent<HTMLDivElement>,
    args: StandardTableOnKeyDownArgs<TItem, TColumnKey>,
  ) => void;
  disableGridCell?: boolean;
  disableGridCellFocus?: boolean;
  gridCellOptions?: Omit<
    UseGridCellOptions<string>,
    | "colIndex"
    | "rowIndex"
    | "numRows"
    | "numCols"
    | "tableId"
    | "isEditable"
    | "onChange"
  >;
  sortOrderIconVariant?: SortOrderIconVariant;
  renderSummaryCell?: StandardTableSummaryCellRenderer<TItem>;
  summaryText?: StandardTableSummaryTextProvider<TItem>;
  summaryCellColSpan?: number;
}
```

## Features

### Sorting

- Internal and external sorting support
- Custom sort order icons
- Sort direction indicators
- Disable sorting per column or globally

### Selection

- Row selection with checkboxes
- Header checkbox for selecting all rows
- Disable selection per row
- Custom selection state management

### Column Groups

- Group columns under headers
- Sticky column groups
- Custom group ordering
- Group-specific styling

### Sticky Elements

- Sticky headers
- Sticky columns
- Sticky checkbox column
- Custom z-index control

### Row Expansion

- Expandable rows
- Custom expansion content
- Disable expansion per row
- Expand/collapse all functionality

### Cell Editing

- Editable cells
- Custom cell renderers
- Grid cell navigation
- Keyboard support

### Summary Row

- Custom summary cell renderers
- Summary text providers
- Column span control
- Conditional rendering

## Best Practices

1. Use appropriate column widths and min-widths to ensure good layout
2. Implement proper key resolvers for efficient rendering
3. Use sticky headers for long tables
4. Consider accessibility when implementing custom cell renderers
5. Use appropriate text sizes for different table variants
6. Implement proper error handling and loading states
7. Use column groups for better organization of related columns
8. Consider performance when implementing row expansion
9. Use appropriate sorting strategies based on data size
10. Implement proper keyboard navigation support

## Accessibility

- Keyboard navigation support
- ARIA attributes for table structure
- Focus management
- Screen reader support
- High contrast support
- Keyboard shortcuts

## Styling

The table supports various styling options:

1. Table variants:

   - Relaxed
   - Standard
   - Condensed
   - Compact

2. Column styling:

   - Background colors
   - Borders
   - Alignment
   - Widths
   - Custom cell renderers

3. Row styling:

   - Background colors
   - Hover states
   - Selection states
   - Expansion states

4. Header styling:
   - Custom labels
   - Tooltips
   - Sort indicators
   - Group headers

## Integration Example

```typescript
import { StandardTable } from "@stenajs-webui/grid";

interface User {
  id: string;
  name: string;
  email: string;
  role: string;
}

const users: User[] = [
  { id: "1", name: "John Doe", email: "john@example.com", role: "Admin" },
  { id: "2", name: "Jane Smith", email: "jane@example.com", role: "User" },
];

const config: StandardTableConfig<User, keyof User> = {
  keyResolver: (item) => item.id,
  columns: {
    name: {
      columnLabel: "Name",
      itemValueResolver: (item) => item.name,
      width: "200px",
    },
    email: {
      columnLabel: "Email",
      itemValueResolver: (item) => item.email,
      width: "250px",
    },
    role: {
      columnLabel: "Role",
      itemValueResolver: (item) => item.role,
      width: "150px",
    },
  },
  columnOrder: ["name", "email", "role"],
  showRowCheckbox: true,
  stickyHeader: true,
};

const UserTable = () => {
  return <StandardTable config={config} items={users} />;
};
```
