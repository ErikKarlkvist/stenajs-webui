# Grid Export Package

The grid-export package provides components and utilities for exporting data from the StandardTable component to Excel and copying table content to the clipboard in HTML format.

## Components

### StandardTableExcelExportButton

A button component that exports the table data to an Excel file.

#### Props

```typescript
interface StandardTableExcelExportButtonProps<
  TItem extends object,
  TColumnKey extends string,
  TColumnGroupKey extends string,
> extends Pick<
      StandardTableProps<TItem, TColumnKey, TColumnGroupKey>,
      "config" | "items"
    >,
    Pick<FlatButtonProps, "size"> {
  filename?: string; // Default: "exported-spreadsheet"
  formatters?: CustomCellFormatters<TItem, TColumnKey>;
}
```

#### Example Usage

```tsx
import { StandardTableExcelExportButton } from "@stenajs-webui/grid-export";

const UserTableExport = () => {
  return (
    <StandardTableExcelExportButton
      config={tableConfig}
      items={users}
      filename="user-list"
      formatters={{
        role: (value) => value.toUpperCase(),
        email: (value) => value.toLowerCase(),
      }}
    />
  );
};
```

### StandardTableHtmlCopyToClipboardButton

A button component that copies the table content to the clipboard in HTML format.

#### Props

```typescript
interface StandardTableHtmlCopyToClipboardButtonProps<
  TItem extends object,
  TColumnKey extends string,
  TColumnGroupKey extends string,
> extends Pick<
      StandardTableProps<TItem, TColumnKey, TColumnGroupKey>,
      "config" | "items"
    >,
    Pick<FlatButtonProps, "size"> {
  formatters?: CustomCellFormatters<TItem, TColumnKey>;
  renderContent?: (content: string) => string | null;
  label?: string; // Default: "Copy to clipboard"
  labelAfterCopy?: string; // Default: "Content copied!"
  numTimeToRevertLabel?: number; // Default: 2000
}
```

#### Example Usage

```tsx
import { StandardTableHtmlCopyToClipboardButton } from "@stenajs-webui/grid-export";

const UserTableCopy = () => {
  return (
    <StandardTableHtmlCopyToClipboardButton
      config={tableConfig}
      items={users}
      label="Copy user list"
      labelAfterCopy="Copied to clipboard!"
      formatters={{
        role: (value) => value.toUpperCase(),
        email: (value) => value.toLowerCase(),
      }}
    />
  );
};
```

## Utilities

### Excel Downloader

The `downloadExcelForStandardTable` utility function handles the Excel export process.

#### Parameters

- `filename: string` - The name of the exported file
- `config: StandardTableConfig` - The table configuration
- `items: Array<TItem>` - The table data
- `formatters?: CustomCellFormatters` - Optional cell formatters

### Copy Content to Clipboard

The `copyContentToClipboard` utility function handles copying table content to the clipboard.

#### Parameters

- `items: Array<TItem>` - The table data
- `config: StandardTableConfig` - The table configuration
- `formatters?: CustomCellFormatters` - Optional cell formatters
- `renderContent?: (content: string) => string | null` - Optional content transformer

## Custom Cell Formatters

You can provide custom formatters for specific columns to transform the data before export or copy.

### Example Formatters

```typescript
const formatters: CustomCellFormatters<User, keyof User> = {
  // Format role as uppercase
  role: (value) => value.toUpperCase(),
  
  // Format email as lowercase
  email: (value) => value.toLowerCase(),
  
  // Format date
  createdAt: (value) => new Date(value).toLocaleDateString(),
  
  // Format currency
  salary: (value) => `$${value.toLocaleString()}`,
};
```

## Best Practices

1. Use meaningful filenames for Excel exports
2. Implement appropriate cell formatters for data transformation
3. Consider data size when exporting to Excel
4. Use appropriate button labels and feedback messages
5. Handle empty data states gracefully
6. Consider performance when formatting large datasets
7. Test export functionality with different data types
8. Ensure proper error handling
9. Consider accessibility when implementing custom formatters
10. Use appropriate button sizes and icons

## Accessibility

- All components support keyboard navigation
- ARIA attributes are included where appropriate
- Focus management is handled properly
- Button states are clearly indicated
- Feedback messages are accessible

## Styling

Components can be styled using:
- CSS modules
- Theme variables
- Inline styles
- Custom class names

## Integration Example

```tsx
import { StandardTable } from "@stenajs-webui/grid";
import {
  StandardTableExcelExportButton,
  StandardTableHtmlCopyToClipboardButton,
} from "@stenajs-webui/grid-export";

const UserTable = () => {
  const formatters = {
    role: (value) => value.toUpperCase(),
    email: (value) => value.toLowerCase(),
    createdAt: (value) => new Date(value).toLocaleDateString(),
  };

  return (
    <div>
      <div style={{ marginBottom: "1rem" }}>
        <StandardTableExcelExportButton
          config={tableConfig}
          items={users}
          filename="user-list"
          formatters={formatters}
        />
        <StandardTableHtmlCopyToClipboardButton
          config={tableConfig}
          items={users}
          formatters={formatters}
        />
      </div>
      <StandardTable config={tableConfig} items={users} />
    </div>
  );
};
```