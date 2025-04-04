# Redux

## Overview

The redux package provides a comprehensive set of Redux utilities, reducer factories, and higher-order reducers for managing application state. It includes tools for handling common state management patterns like CRUD operations, entity management, sorting, and selection.

## Features

### Entity Management

#### Entity Reducer

Factory for creating reducers that manage a single entity.

```tsx
import { createEntityReducer, createEntityActions } from "@stenajs-webui/redux";

const entityReducer = createEntityReducer<MyEntity>();
const { setEntity, clearEntity } = createEntityActions<MyEntity>("myEntity");
```

#### Entity By ID Reducer

Factory for creating reducers that manage multiple entities by ID.

```tsx
import {
  createEntityByIdReducer,
  createEntityByIdActions,
} from "@stenajs-webui/redux";

const entityByIdReducer = createEntityByIdReducer<MyEntity>();
const { setEntityById, removeEntityById } =
  createEntityByIdActions<MyEntity>("myEntities");
```

#### Entity List Reducer

Higher-order reducer for managing lists of entities.

```tsx
import {
  createEntityListReducer,
  createEntityListActions,
} from "@stenajs-webui/redux";

const entityListReducer = createEntityListReducer<MyEntity>();
const { addEntity, removeEntity, updateEntity } =
  createEntityListActions<MyEntity>("myEntityList");
```

### Selection Management

#### Selected IDs Reducer

Factory for managing selected IDs in lists.

```tsx
import {
  createSelectedIdsReducer,
  createSelectedIdsActions,
} from "@stenajs-webui/redux";

const selectedIdsReducer = createSelectedIdsReducer();
const { selectId, deselectId, toggleId } =
  createSelectedIdsActions("mySelectedIds");
```

### Sorting Management

#### Sort Order Reducer

Factory for managing sort order state.

```tsx
import {
  createSortOrderReducer,
  createSortOrderActions,
} from "@stenajs-webui/redux";

const sortOrderReducer = createSortOrderReducer();
const { setSortOrder, toggleSortOrder } = createSortOrderActions("mySortOrder");
```

#### Sort Order By ID Reducer

Factory for managing sort order state for multiple entities.

```tsx
import {
  createSortOrderByIdReducer,
  createSortOrderByIdActions,
} from "@stenajs-webui/redux";

const sortOrderByIdReducer = createSortOrderByIdReducer();
const { setSortOrderById, toggleSortOrderById } =
  createSortOrderByIdActions("mySortOrders");
```

### Value Management

#### Value By ID Reducer

Factory for managing values by ID.

```tsx
import {
  createValueByIdReducer,
  createValueByIdActions,
} from "@stenajs-webui/redux";

const valueByIdReducer = createValueByIdReducer<string>();
const { setValueById, removeValueById } =
  createValueByIdActions<string>("myValues");
```

### CRUD Status Management

#### Entity CRUD Status Reducer

Factory for managing CRUD operation status.

```tsx
import { createEntityCrudStatusReducer } from "@stenajs-webui/redux";

const entityCrudStatusReducer = createEntityCrudStatusReducer("myEntityStatus");
```

### Field Management

#### Modified Field Reducer

Factory for tracking modified fields.

```tsx
import { createModifiedFieldReducer } from "@stenajs-webui/redux";

const modifiedFieldReducer = createModifiedFieldReducer("myModifiedFields");
```

### Commit Management

#### Commit Reducer

Factory for managing commit operations.

```tsx
import { createCommitReducer, createCommitActions } from "@stenajs-webui/redux";

const commitReducer = createCommitReducer();
const { commit, rollback } = createCommitActions("myCommits");
```

### Editable Entity Management

#### Editable Entity Reducer

Factory for managing editable entities.

```tsx
import {
  createEditableEntityReducer,
  createEditableEntityActions,
} from "@stenajs-webui/redux";

const editableEntityReducer = createEditableEntityReducer<MyEntity>();
const { setEditableEntity, updateEditableEntity } =
  createEditableEntityActions<MyEntity>("myEditableEntity");
```

## Usage Examples

### Basic Entity Management

```tsx
import { createStore, combineReducers } from "redux";
import { createEntityReducer, createEntityActions } from "@stenajs-webui/redux";

// Create reducer and actions
const entityReducer = createEntityReducer<MyEntity>();
const { setEntity, clearEntity } = createEntityActions<MyEntity>("myEntity");

// Create store
const rootReducer = combineReducers({
  myEntity: entityReducer,
});

const store = createStore(rootReducer);

// Dispatch actions
store.dispatch(setEntity({ id: "1", name: "My Entity" }));
store.dispatch(clearEntity());
```

### Entity List with Selection

```tsx
import { createStore, combineReducers } from "redux";
import {
  createEntityListReducer,
  createEntityListActions,
  createSelectedIdsReducer,
  createSelectedIdsActions,
} from "@stenajs-webui/redux";

// Create reducers and actions
const entityListReducer = createEntityListReducer<MyEntity>();
const selectedIdsReducer = createSelectedIdsReducer();

const { addEntity, removeEntity } =
  createEntityListActions<MyEntity>("myEntityList");
const { selectId, deselectId } = createSelectedIdsActions("mySelectedIds");

// Create store
const rootReducer = combineReducers({
  myEntityList: entityListReducer,
  mySelectedIds: selectedIdsReducer,
});

const store = createStore(rootReducer);

// Dispatch actions
store.dispatch(addEntity({ id: "1", name: "Entity 1" }));
store.dispatch(selectId("1"));
```

### Sortable List

```tsx
import { createStore, combineReducers } from "redux";
import {
  createEntityListReducer,
  createEntityListActions,
  createSortOrderReducer,
  createSortOrderActions,
} from "@stenajs-webui/redux";

// Create reducers and actions
const entityListReducer = createEntityListReducer<MyEntity>();
const sortOrderReducer = createSortOrderReducer();

const { addEntity } = createEntityListActions<MyEntity>("myEntityList");
const { setSortOrder } = createSortOrderActions("mySortOrder");

// Create store
const rootReducer = combineReducers({
  myEntityList: entityListReducer,
  mySortOrder: sortOrderReducer,
});

const store = createStore(rootReducer);

// Dispatch actions
store.dispatch(addEntity({ id: "1", name: "Entity 1" }));
store.dispatch(setSortOrder({ field: "name", direction: "asc" }));
```

## Best Practices

1. Use appropriate reducer factories for your use case
2. Keep action types unique across your application
3. Use selectors for accessing state
4. Keep reducers pure and side-effect free
5. Use TypeScript for type safety
6. Consider using middleware for side effects
7. Keep state normalized when possible

## Type Safety

The package is built with TypeScript and provides full type safety:

```tsx
interface MyEntity {
  id: string;
  name: string;
}

const entityReducer = createEntityReducer<MyEntity>();
const { setEntity } = createEntityActions<MyEntity>("myEntity");

// TypeScript will ensure type safety
store.dispatch(setEntity({ id: "1", name: "My Entity" })); // OK
store.dispatch(setEntity({ id: "1" })); // Error: missing name property
```

## Integration with React

The reducers and actions can be used with React Redux:

```tsx
import { useSelector, useDispatch } from "react-redux";
import { createEntityReducer, createEntityActions } from "@stenajs-webui/redux";

const { setEntity } = createEntityActions<MyEntity>("myEntity");

const MyComponent = () => {
  const dispatch = useDispatch();
  const entity = useSelector((state) => state.myEntity);

  return (
    <button
      onClick={() => dispatch(setEntity({ id: "1", name: "New Entity" }))}
    >
      Set Entity
    </button>
  );
};
```
