# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

# Google Sheets Clone

## Overview
This project is a web-based spreadsheet application inspired by Google Sheets. It provides an interactive grid where users can enter, format, and process data using various spreadsheet functionalities.

## Features
- **Spreadsheet-like Grid**: Handsontable-powered interface for seamless interaction.
- **Cell Formatting**: Bold, Italics, Font Size, Font Color.
- **Conditional Formatting**: Apply different styles based on cell values.
- **Advanced Formulas**: HyperFormula integration for complex calculations.
- **Custom Cell Rendering**: Modify cell display dynamically.
- **Dropdown Menus**: Provide predefined selections for specific columns.
- **Keyboard Shortcuts**: Improve user efficiency.
- **Drag-to-Fill**: Extend values/formats across cells.
- **Merged Cells Support**: Format multiple selected cells as one.
- **Context Menu**: Right-click menu for additional operations.

---

## Tech Stack
### Frontend
- **React.js**: Component-based UI.
- **Handsontable**: Provides the spreadsheet functionality.
- **HyperFormula**: Enables formula evaluation.
- **Context API**: Manages formatting state.
- **CSS**: Styling and layout adjustments.

### Backend
- **Node.js & Express.js**: API handling and backend logic.
- **MongoDB**: Persistent storage for spreadsheets.

---

## Project Structure
```
root/
├── public/             # Static assets
├── src/
│   ├── components/
│   │   ├── Grid.js         # Spreadsheet component
│   │   ├── Formulabar.js   # Toolbar with formatting buttons
│   │   ├── Sidebar.js      # Additional options (future enhancement)
│   ├── context/
│   │   ├── FormattingContext.js # Context API for formatting state
│   ├── styles/
│   │   ├── Grid.css        # Grid styles
│   │   ├── Formulabar.css  # Toolbar styles
│   ├── App.js              # Main app component
│   ├── index.js            # Entry point
├── server/
│   ├── models/             # Database models
│   ├── routes/             # API endpoints
│   ├── server.js           # Express server
├── package.json           # Dependencies and scripts
└── README.md              # Project documentation
```

---

## Application Flow
1. **User loads the application**
   - React renders the `Grid` and `Formulabar` components.
   - Handsontable initializes a blank spreadsheet.
2. **User interacts with the grid**
   - Typing in a cell updates the **2D array state**.
   - Selecting a cell stores the selection.
3. **User applies formatting**
   - Clicks `B` (bold), `I` (italic), etc.
   - Selected cells update using `setCellMeta()`.
4. **User enters a formula**
   - HyperFormula processes calculations.
   - Dependencies update automatically.
5. **User saves data**
   - Backend stores grid state in MongoDB.
6. **User reopens spreadsheet**
   - Data is fetched and displayed in Handsontable.

---

## Data Structures Used
### 1. **2D Array for Spreadsheet Data**
```js
const [data, setData] = useState(
  Array.from({ length: 1000 }, () => Array(52).fill(""))
);
```
- Efficient row/column access.
- Supports fast cell updates.

### 2. **Object-based Metadata for Formatting**
```js
hot.setCellMeta(row, col, "className", "bold");
```
- Keeps styling separate from data.
- Enables per-cell formatting.

### 3. **Context API for Global State**
```js
const [formatting, setFormatting] = useState({ bold: false });
```
- Centralized UI state management.

### 4. **HyperFormula for Formula Processing**
- Uses **hash maps** for caching formulas.
- Ensures recalculations happen efficiently.

## Accuracy of Data and Mathematical Implementation
- **Formula Handling**: HyperFormula ensures accurate calculations.
- **Floating-Point Precision Fix**: Prevents rounding errors in calculations.
- **Optimized Performance**:
  - Batch updates prevent excessive re-renders.
  - Handsontable efficiently handles large data sets.



## Conclusion
This project replicates core Google Sheets functionalities while optimizing for performance and usability. It utilizes React, Handsontable, and HyperFormula to deliver a powerful spreadsheet experience in a web application.


