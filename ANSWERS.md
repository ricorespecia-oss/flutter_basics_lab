# Flutter Basics Lab — Answers

## 1. GitHub Repository

GitHub Repository: https://github.com/ricorespecia-oss/flutter_basics_lab

## 2. Activity 2 — Debug Console

Last three `build()` lines:

```text
build() called: 4 glasses
build() called: 5 glasses
build() called: 6 glasses
```

## 3. Experiment Observations

### Activity 2 — Changing `_glasses` Outside `setState()`

When I changed `_glasses` outside `setState()`, the screen did not immediately update because Flutter was not notified that the state had changed. Using `setState()` tells Flutter to rebuild the widget and display the updated number of glasses.

### Activity 3 — Removing `Expanded`

When I removed `Expanded` from a `StatBox`, the boxes no longer shared the available horizontal space equally. `Expanded` allows each box to take an equal share of the available space in the `Row`, helping the weather dashboard display properly.

### Activity 5 — Changing the Button Border Radius

When I changed `BorderRadius.circular(8)` to `BorderRadius.circular(20)`, the button corners became more rounded. This showed how changing a widget's style can affect its appearance.

## 4. Review Questions

### 1. What is the difference between a StatelessWidget and a StatefulWidget? Give one example of each from this lab.

A `StatelessWidget` does not manage changing state within itself, while a `StatefulWidget` can update its interface when its state changes. An example of a `StatelessWidget` is the profile card in Activity 1, while the water tracker in Activity 2 uses a `StatefulWidget`.

### 2. Why is a StatefulWidget written as two classes? What does each class do?

A `StatefulWidget` uses two classes to separate the widget's configuration from its changing state. The first class defines the widget, while the second class extends `State` and manages the data and rebuilding of the interface.

### 3. In Activity 2, what happened when you changed `_glasses` outside `setState()`? Why?

The screen did not immediately reflect the changed value because Flutter was not notified to rebuild the widget. `setState()` notifies Flutter that the state has changed and the interface needs updating.

### 4. Looking at the Debug Console in Activity 2, when is `build()` called?

The `build()` method is called when Flutter needs to create or update the widget's interface. In Activity 2, it runs when the screen is initially displayed and again when state changes trigger a rebuild.

### 5. Explain the main axis and the cross axis of a Row and of a Column.

In a `Row`, the main axis is horizontal and the cross axis is vertical. In a `Column`, the main axis is vertical and the cross axis is horizontal.

### 6. In Activity 3, what happened when you removed Expanded from a StatBox? What does Expanded do?

Without `Expanded`, the `StatBox` widgets no longer divided the available horizontal space equally. `Expanded` makes a child take up a share of the remaining space in a `Row` or `Column`.

### 7. Why do we use GridView.builder for the menu instead of a Column with many children?

`GridView.builder` displays menu items in a grid and can build items as they are needed. It is more suitable for a large or scrollable menu because it manages the grid layout efficiently, unlike a simple `Column` that places children vertically.

### 8. How do Stack and Positioned create the Best seller badge in Activity 4?

`Stack` allows widgets to overlap each other. `Positioned` places the Best seller badge at a specific location on top of the menu card, allowing the badge to appear over the item without changing the overall grid layout.

### 9. What is the difference between customizing with ThemeData and with a style on one widget? Give one example of each from Activity 5.

`ThemeData` defines the app's overall appearance, including its color scheme and brightness. For example, Activity 5 uses `ThemeData` to configure the light and dark themes. A style applied to one widget changes that widget specifically, such as changing the button's border radius from 8 to 20.

### 10. When you flip the dark-mode switch in Activity 5, which widget holds the state, and how does the change reach MaterialApp?

The `_ThemeDemoAppState` class holds the `_isDark` Boolean state. When the switch changes, its callback calls `setState()`, which rebuilds the app and updates `MaterialApp`'s `themeMode` to either `ThemeMode.light` or `ThemeMode.dark`.
