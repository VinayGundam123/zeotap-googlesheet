# Spreadsheet Web Application

## Overview
This project is a web-based spreadsheet application inspired by Google Sheets. It provides an interactive grid with support for formulas, data formatting, and a customizable toolbar. The application is built using the MERN stack with React on the frontend and Handsontable for handling spreadsheet functionalities.

## Features
- **Spreadsheet Grid:** Implements Handsontable for an interactive grid layout.
- **Formula Support:** Uses HyperFormula for executing mathematical expressions.
- **Toolbar:** Provides text formatting options like bold, italics, underline, and font size adjustments.
- **Formula Bar:** Allows users to enter and manipulate formulas.
- **Bottom Bar:** Placeholder component for additional functionalities.
- **Context Provider:** Uses React Context API to manage formatting state across components.

## Tech Stack
- **Frontend:** React.js
- **Spreadsheet Engine:** Handsontable & HyperFormula
- **State Management:** React Context API
- **Styling:** CSS Modules

## Project Structure
```
├── src
│   ├── components
│   │   ├── Toolbar.js
│   │   ├── Formulabar.js
│   │   ├── Grid.js
│   │   ├── Bottombar.js
│   ├── context
│   │   ├── FormattingContext.js
│   ├── App.js
│   ├── SpreadsheetGrid.js
│   ├── index.js
```

### Component Breakdown
1. **App.js**
   - Renders the `SpreadsheetGrid` component.

2. **SpreadsheetGrid.js**
   - Combines all major components: `Toolbar`, `Formulabar`, `Grid`, and `Bottombar`.
   - Wraps components inside `FormattingProvider` to manage formatting state.

3. **Toolbar.js**
   - Displays the spreadsheet title.
   - Provides menu options like File, Edit, View, Insert, etc.
   - Allows renaming of the spreadsheet.

4. **Formulabar.js**
   - Offers buttons for text formatting (bold, italic, underline).
   - Controls font size and color selection.

5. **Grid.js**
   - Implements the Handsontable grid for data entry.
   - Supports formulas, context menu, and formatting features.
   - Utilizes `afterChangeHandler` and `afterSelectionHandler` to apply custom styling.

6. **Bottombar.js**
   - Placeholder component for potential future features.

## Installation
### Prerequisites
Ensure you have Node.js installed.

### Steps
1. Clone the repository:
   ```sh
   git clone https://github.com/VinayGundam123/Share-favorite-place.git
   ```
2. Navigate to the project directory:
   ```sh
   cd Share-favorite-place
   ```
3. Install dependencies:
   ```sh
   npm install
   ```
4. Start the development server:
   ```sh
   npm start
   ```

## Usage
- Click on the spreadsheet title to rename it.
- Enter data into the grid, apply formulas, and format text using the toolbar.
- Use the formula bar to modify text styles and font sizes dynamically.

## Additional Modules
This project uses the following external libraries:
- `handsontable` - For rendering the spreadsheet grid.
- `hyperformula` - To enable formula calculations.

To manually install these dependencies, run:
```sh
npm install handsontable hyperformula
```

## Future Improvements
- Implementing advanced spreadsheet functionalities.
- Adding data export/import options.
- Enhancing UI/UX to further match Google Sheets.

## License
This project is licensed under the MIT License.

