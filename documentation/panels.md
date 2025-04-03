# Panels Package Documentation

The panels package provides a collection of UI components for building application layouts and navigation systems. It includes components for navigation bars, sidebars, notifications, and various panel types.

## Components

### NavBar

A navigation bar component that can be customized with left, center, and right sections.

#### Props

- `className?: string` - Additional CSS class name
- `showMenuButton?: boolean` - Whether to show the menu button
- `onClickMenuButton?: () => void` - Callback when menu button is clicked
- `right?: ReactNode` - Content to display on the right side
- `center?: ReactNode` - Content to display in the center
- `left?: ReactNode` - Content to display on the left side
- `variant?: "compact" | "standard" | "relaxed"` - Visual variant of the navbar
- `children?: ReactNode` - Additional content

#### Example Usage

```tsx
<NavBar
  showMenuButton
  onClickMenuButton={handleMenuClick}
  left={<Logo />}
  center={<SearchBar />}
  right={<UserMenu />}
  variant="standard"
>
  <NavBarButton label="Home" />
  <NavBarButton label="About" />
</NavBar>
```

### SidebarMenu

A collapsible sidebar menu component with pin functionality.

#### Props

- `className?: string` - Additional CSS class name
- `onCloseClick?: () => void` - Callback when close button is clicked
- `pinButtonVisible?: boolean` - Whether to show the pin button
- `isPinned?: boolean` - Whether the sidebar is pinned
- `bottomItems?: ReactNode` - Content to display at the bottom of the sidebar
- `onClickPinButton?: () => void` - Callback when pin button is clicked
- `children?: ReactNode` - Menu items

#### Example Usage

```tsx
<SidebarMenu
  onCloseClick={handleClose}
  pinButtonVisible
  isPinned={isPinned}
  onClickPinButton={handlePinToggle}
  bottomItems={<LogoutButton />}
>
  <SidebarMenuLink label="Dashboard" icon={<DashboardIcon />} />
  <SidebarMenuCollapsible label="Settings">
    <SidebarMenuLink label="Profile" />
    <SidebarMenuLink label="Preferences" />
  </SidebarMenuCollapsible>
</SidebarMenu>
```

### NotificationList

A container for displaying notifications.

#### Props

- `children?: ReactNode` - Notification items

#### Example Usage

```tsx
<NotificationList>
  <Notification
    title="New Message"
    content="You have received a new message"
    timestamp="2 minutes ago"
  />
  <Notification
    title="System Update"
    content="System maintenance scheduled"
    timestamp="1 hour ago"
  />
</NotificationList>
```

### ErrorPanel

A panel for displaying error messages.

#### Props

- `className?: string` - Additional CSS class name
- `children?: ReactNode` - Error content

#### Example Usage

```tsx
<ErrorPanel>
  <h2>Something went wrong</h2>
  <p>Please try again later</p>
</ErrorPanel>
```

### LoadingPanel

A panel for displaying loading states.

#### Props

- `className?: string` - Additional CSS class name
- `children?: ReactNode` - Loading content

#### Example Usage

```tsx
<LoadingPanel>
  <p>Loading data...</p>
</LoadingPanel>
```

### PageHeader

A header component for pages.

#### Props

- `className?: string` - Additional CSS class name
- `children?: ReactNode` - Header content

#### Example Usage

```tsx
<PageHeader>
  <PageHeading>Dashboard</PageHeading>
  <PageHeaderRow>
    <ActionMenuPrimaryButton label="Create" />
  </PageHeaderRow>
</PageHeader>
```

### Collapsible

A collapsible panel component.

#### Props

- `className?: string` - Additional CSS class name
- `label: string` - Label for the collapsible section
- `children?: ReactNode` - Content to be collapsible
- `isOpen?: boolean` - Whether the section is open
- `onToggle?: () => void` - Callback when section is toggled

#### Example Usage

```tsx
<Collapsible label="Advanced Settings" isOpen={isOpen} onToggle={handleToggle}>
  <SettingsForm />
</Collapsible>
```

## Best Practices

1. Use NavBar for consistent navigation across your application
2. Implement SidebarMenu for hierarchical navigation
3. Use NotificationList for displaying system notifications
4. Utilize ErrorPanel and LoadingPanel for error and loading states
5. Use PageHeader for consistent page layouts
6. Implement Collapsible for organizing content sections

## Accessibility

- All components support keyboard navigation
- ARIA attributes are included for screen readers
- Focus management is handled appropriately
- Color contrast meets accessibility standards

## Styling

Components can be styled using:
- CSS modules
- Class name props
- Theme customization

## Integration

Components can be used together to create complete layouts:

```tsx
<>
  <NavBar
    showMenuButton
    onClickMenuButton={handleMenuClick}
    left={<Logo />}
    right={<NotificationButton />}
  />
  <Row>
    <SidebarMenu
      onCloseClick={handleClose}
      pinButtonVisible
      isPinned={isPinned}
    >
      <SidebarMenuLink label="Home" />
      <SidebarMenuLink label="Settings" />
    </SidebarMenu>
    <Column flex={1}>
      <PageHeader>
        <PageHeading>Dashboard</PageHeading>
      </PageHeader>
      <Box indent={2}>
        <Collapsible label="Statistics">
          <StatisticsPanel />
        </Collapsible>
      </Box>
    </Column>
  </Row>
</>
``` 