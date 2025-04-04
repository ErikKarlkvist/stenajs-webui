# Modal Package Documentation

The modal package provides a comprehensive set of components for creating modal dialogs, drawers, and windows in your application. It includes both declarative and imperative approaches to modal management.

## Declarative Modals

### Modal

A basic modal dialog component.

#### Props

- `isOpen: boolean` - Controls the visibility of the modal
- `onRequestClose?: () => void` - Callback when modal is requested to close
- `background?: string` - Background color of the modal
- `children?: ReactNode` - Modal content
- `shouldCloseOnOverlayClick?: boolean` - Whether clicking the overlay closes the modal
- `shouldCloseOnEsc?: boolean` - Whether pressing Escape closes the modal

#### Example Usage

```tsx
const [isOpen, setIsOpen] = useState(false);

<Modal
  isOpen={isOpen}
  onRequestClose={() => setIsOpen(false)}
  background="var(--swui-background-color)"
>
  <ModalHeader>Title</ModalHeader>
  <ModalBody>
    <p>Modal content goes here</p>
  </ModalBody>
  <ModalFooter>
    <ButtonGroup spacing={1}>
      <PrimaryButton label="Save" onClick={handleSave} />
      <SecondaryButton label="Cancel" onClick={() => setIsOpen(false)} />
    </ButtonGroup>
  </ModalFooter>
</Modal>;
```

### Drawer

A sliding panel component that can appear from any side of the screen.

#### Props

- `isOpen: boolean` - Controls the visibility of the drawer
- `onRequestClose?: () => void` - Callback when drawer is requested to close
- `slideFrom?: "left" | "right" | "top" | "bottom"` - Direction from which the drawer slides
- `width?: string` - Width of the drawer (for left/right drawers)
- `height?: string` - Height of the drawer (for top/bottom drawers)
- `background?: string` - Background color
- `floating?: boolean` - Whether the drawer floats with a gap from the viewport
- `zIndex?: number` - z-index of the drawer
- `portalTarget?: HTMLElement` - Element to portal the drawer into

#### Example Usage

```tsx
const [isOpen, setIsOpen] = useState(false);

<Drawer
  isOpen={isOpen}
  onRequestClose={() => setIsOpen(false)}
  slideFrom="right"
  width="400px"
  floating
>
  <DrawerHeader>Settings</DrawerHeader>
  <Box spacing={2} indent={2}>
    <p>Drawer content goes here</p>
  </Box>
</Drawer>;
```

### Window

A draggable window component with header and footer.

#### Props

- `isOpen: boolean` - Controls the visibility of the window
- `onRequestClose?: () => void` - Callback when window is requested to close
- `header?: ReactNode` - Custom header content
- `headerText?: string` - Text to display in the header
- `draggable?: boolean` - Whether the window is draggable
- `spacing?: number` - Internal spacing
- `indent?: number` - Internal padding
- `footer?: ReactNode` - Footer content
- `disableStickyFooter?: boolean` - Whether to disable sticky footer behavior

#### Example Usage

```tsx
const [isOpen, setIsOpen] = useState(false);

<Window
  isOpen={isOpen}
  onRequestClose={() => setIsOpen(false)}
  headerText="Edit User"
  draggable
  spacing={2}
  indent={2}
  footer={
    <ButtonGroup spacing={1}>
      <PrimaryButton label="Save" onClick={handleSave} />
      <SecondaryButton label="Cancel" onClick={() => setIsOpen(false)} />
    </ButtonGroup>
  }
>
  <Form>
    <LabelledTextInput label="Name" value={name} onValueChange={setName} />
    <LabelledTextInput label="Email" value={email} onValueChange={setEmail} />
  </Form>
</Window>;
```

## Imperative Modals

### UseDialog

A hook for managing dialogs imperatively.

#### Example Usage

```tsx
const { showDialog, hideDialog } = useDialog();

const handleShowDialog = () => {
  showDialog({
    content: <p>Dialog content</p>,
    onClose: () => hideDialog(),
  });
};
```

### UseAlertDialog

A hook for showing alert dialogs.

#### Example Usage

```tsx
const { showAlert } = useAlertDialog();

const handleShowAlert = () => {
  showAlert({
    title: "Warning",
    content: "Are you sure you want to proceed?",
    confirmLabel: "Yes",
    cancelLabel: "No",
    onConfirm: handleConfirm,
  });
};
```

### UseDrawerDialog

A hook for showing drawer dialogs.

#### Example Usage

```tsx
const { showDrawer } = useDrawerDialog();

const handleShowDrawer = () => {
  showDrawer({
    content: <p>Drawer content</p>,
    slideFrom: "right",
    width: "400px",
  });
};
```

## Building Blocks

### ModalContainer

A container component for modals.

#### Props

- `children?: ReactNode` - Modal content
- `background?: string` - Background color

#### Example Usage

```tsx
<ModalContainer background="var(--swui-background-color)">
  <ModalHeader>Title</ModalHeader>
  <ModalBody>Content</ModalBody>
</ModalContainer>
```

### ModalHeader

A header component for modals.

#### Props

- `children?: ReactNode` - Header content
- `onClose?: () => void` - Callback when close button is clicked

#### Example Usage

```tsx
<ModalHeader onClose={handleClose}>
  <Text variant="bold">Modal Title</Text>
</ModalHeader>
```

### ModalBody

A body component for modals.

#### Props

- `children?: ReactNode` - Body content

#### Example Usage

```tsx
<ModalBody>
  <p>Modal content goes here</p>
</ModalBody>
```

### ModalFooter

A footer component for modals.

#### Props

- `children?: ReactNode` - Footer content

#### Example Usage

```tsx
<ModalFooter>
  <ButtonGroup spacing={1}>
    <PrimaryButton label="Save" />
    <SecondaryButton label="Cancel" />
  </ButtonGroup>
</ModalFooter>
```

## Best Practices

1. Use appropriate modal type based on content and interaction needs
2. Implement proper keyboard navigation
3. Handle focus management correctly
4. Use portals for proper stacking context
5. Consider mobile responsiveness
6. Implement proper animations
7. Handle escape key and overlay clicks
8. Use appropriate z-index values

## Accessibility

- All components support keyboard navigation
- ARIA attributes are included for screen readers
- Focus management is handled properly
- Color contrast meets accessibility standards
- Modal content is properly announced

## Styling

Components can be styled using:

- CSS modules
- Theme variables
- Inline styles
- Custom class names

## Integration

Components can be used together to create complex modal interfaces:

```tsx
<Window
  isOpen={isOpen}
  onRequestClose={() => setIsOpen(false)}
  headerText="User Profile"
  draggable
>
  <Box spacing={2} indent={2}>
    <Row gap={2} alignItems="center">
      <CircledIcon
        icon={faUser}
        size={48}
        background="var(--swui-primary-color)"
        color="white"
      />
      <Column>
        <Text variant="bold">John Doe</Text>
        <Text>john.doe@example.com</Text>
      </Column>
    </Row>
    <Form>
      <LabelledTextInput label="Name" value={name} onValueChange={setName} />
      <LabelledTextInput label="Email" value={email} onValueChange={setEmail} />
    </Form>
  </Box>
  <ModalFooter>
    <ButtonGroup spacing={1}>
      <PrimaryButton label="Save" onClick={handleSave} />
      <SecondaryButton label="Cancel" onClick={() => setIsOpen(false)} />
    </ButtonGroup>
  </ModalFooter>
</Window>
```
