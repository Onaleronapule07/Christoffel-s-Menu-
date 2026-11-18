# Christoffel-s-Menu-

Christoffel's Menu App is a React Native mobile app for a chef to manage a restaurant menu instead of using handwritten paper menus. The screens use large readable texts, clearly labelled fields and obvious buttons so that a non-technical user can use it easily.

# Apps Features
* A home screen with a live updating list of menu itemsand helpful empty-state messages.
* An add menu item (dish name, description, course and price) with validation.
* An edit and update an existing menu item
* Delete a menu item (with a confirmation prompt)
* A search menu items by name
* Filter menu items by course (Starter, Main Course, Dessert) and clear the search/filter
* A menu statistics screen that displays the total items, average price and number of items per course
* And a success and error messages for all actions

# Link for GitHub:

# Changes since part 2(Change Log)
# New functionality
* I Added edit/update of menu items. The Add screen is extended into MENUFORMSCREEN, which is pre-filled when editing and shows "Update Menu Item" instead of "Save Menu Item".
* Added delete of menu items with an Alert confirmation before deleting.
* Added search by dish name.
* Added filtering by course using filter chips (All, Starter, Main Course, Dessert).
* Added a Statistics screen
* Added a "No matching dishes" empty state for search/filters with no results.
## Refactoring
* Moved menu state out of `App.tsx` into a `MenuProvider` (React Context) with
  `addMenuItem`, `updateMenuItem`, `deleteMenuItem` and `getMenuItemById`, accessed through
  a `useMenu` hook, so screens no longer need props passed down.
* Replaced the manual `useState` screen switching in `App.tsx` with a proper
  React Navigation native stack (Home, MenuForm, Statistics). Fixed the missing imports.
* Created reusable components: `AppButton`, `FormField`, `MenuItemCard`, `SearchBar`,
  `CourseFilter`, `EmptyState` and `StatCard`.
* Created reusable utility functions in `utils/menuUtils.ts`: `filterMenuItems`,
  `calculateStatistics`, `validateMenuForm`, `parsePrice` and `formatPrice`.
* Moved colours and the course list into `constants/theme.ts`, removing repeated values.
* Added a `Course` union type and other shared types in `types.ts`.
* Renamed `onAddItem`/`AddMenuItemScreen` to clearer names (`addMenuItem`/`MenuFormScreen`).

## Validation and user experience improvements
* Validation moved into one function that returns an error for each field.
* Field errors now clear as soon as the user edits that field.
* Price validation uses `Number()` so values such as "12abc" are rejected,
  and comma decimals (e.g. "145,50") are accepted.
* Dish name must be at least 2 characters.
* The price input uses a decimal keypad.
* Added a Cancel button on the form.
* Consistent styling (colours, spacing, button styles) across all screens.
* Accessibility labels added to buttons and inputs.


