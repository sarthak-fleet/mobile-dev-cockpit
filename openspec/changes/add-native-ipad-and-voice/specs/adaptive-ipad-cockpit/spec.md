## ADDED Requirements

### Requirement: Universal iPhone and iPad installation

The iOS application SHALL ship as one universal binary that supports iPhone and iPad without requiring full-screen-only iPad presentation.

#### Scenario: Install on iPad

- **WHEN** the native app is built for a supported iPad
- **THEN** it installs as an iPad application rather than an iPhone compatibility-mode application

#### Scenario: Preserve iPhone presentation

- **WHEN** the same binary runs in a compact iPhone window
- **THEN** the existing phone-focused navigation and safe-area behavior remain usable

### Requirement: Adaptive window layout

The app SHALL derive its compact, intermediate, or regular presentation from the current window dimensions and SHALL preserve the selected project, section, and in-progress text when the window changes size.

#### Scenario: Open a regular-width project workspace

- **WHEN** a project is open in a regular-width iPad window
- **THEN** the app shows persistent leading project/section navigation and a flexible detail workspace at the same time

#### Scenario: Resize to compact width

- **WHEN** an iPad window narrows through Split View or Stage Manager into the compact layout band
- **THEN** navigation collapses to the phone-style presentation without discarding the active section or draft instruction

#### Scenario: Rotate the device

- **WHEN** the user rotates an iPad between portrait and landscape
- **THEN** the layout recomputes from the new window size without clipped controls, inaccessible content, or a route reset

### Requirement: Native-style iPad navigation

The regular-width cockpit SHALL expose a persistent, clearly selected navigation surface for machine state, projects, and the Control, Preview, Agent, Review, and Deploy sections.

#### Scenario: Change project section

- **WHEN** the user selects a different project section from the regular-width navigation surface
- **THEN** the detail pane changes in place and the selected item remains visibly highlighted

#### Scenario: Use pointer or keyboard navigation

- **WHEN** a user operates supported navigation and agent actions with an iPad pointer or hardware keyboard
- **THEN** focus, selection, and activation remain visible and every action also remains available by touch

### Requirement: Workspace-sized preview

The preview SHALL use the available detail workspace on regular-width iPad layouts and SHALL remain isolated from machine credentials and bridge-native message handlers.

#### Scenario: Preview on iPad landscape

- **WHEN** the user opens Preview in a regular-width landscape window
- **THEN** the WebView expands within the detail pane instead of being limited to the phone's fixed preview height

#### Scenario: Preview device shape on iPad

- **WHEN** the user chooses a portrait or landscape preview viewport on iPad
- **THEN** the app changes the in-canvas preview aspect without forcing the iPad's system orientation or disabling multitasking

### Requirement: Accessible resizable content

The iPad interface SHALL respect safe areas, Dynamic Type, minimum touch targets, scrolling, and window resizing across supported orientations and multitasking sizes.

#### Scenario: Increase text size

- **WHEN** the user enables a larger Dynamic Type size
- **THEN** essential labels and actions remain readable and reachable through wrapping or scrolling rather than clipping

#### Scenario: Use a narrow multitasking window

- **WHEN** the app runs in a narrow supported multitasking window
- **THEN** it uses the compact navigation and preserves a scrollable path to every project action
