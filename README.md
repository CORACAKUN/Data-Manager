Data Manager by Coraca

📌 Features

File Upload

Accepts .json and .xlsx/.xls

Auto-detects file type and parses accordingly

Stores original filename for downloads

Table Display

Renders uploaded data into a Bootstrap-styled table

Supports inline editing of cells

Actions column with delete button on every row

Column Reordering

Drag-and-drop column headers to reorder

Saves new order in columnOrder

Action logged in history

Add Row / Add Column

Button to add empty rows

Modal prompt (Bootstrap modal) for adding new columns

Prevents duplicate column names

Search & Sort

Live search: filters rows instantly while typing

Dynamic sorting by column

Type-aware sort:

Numbers sorted numerically

Years detected (YYYY)

Strings sorted alphabetically

History Tracking

Collapsible history log with timestamps

Logs edits, deletes, moves, file uploads, downloads

History counter badge

Undo/Redo system (with stacks)

Undo/Redo

Uses historyStack and redoStack

Can rollback changes or reapply undone changes

Download Data

Export table as JSON or Excel

Current filtered/sorted/edited view is downloaded (not original)

Auto-generates unique filenames (filename_timestamp.json/xlsx)

UI/UX Enhancements

Modern Bootstrap 5 UI

Icons from Bootstrap Icons

History + search/sort hidden until data exists

Confirmation modal on reload

Styled delete button with text + icon

📌 Functions / Logic

File Handling

handleFile(e) → detects file type, reads JSON/Excel

Uses FileReader, XLSX.read, and XLSX.utils.sheet_to_json

Table Rendering

renderTable(view) → builds table dynamically

Supports editable cells with contentEditable

Includes "Delete" button per row

Column Drag & Drop

dragStart(e), dragOver(e), drop(e), dragEnd(e)

Row/Column Management

addRow() → appends blank row

confirmAddColumn() → validates & adds new column via modal

Search/Sort

currentView() → returns data filtered & sorted

applyFilters() → re-renders with applied filters

populateSortOptions() → updates sort dropdown

History & State

logAction(text) → logs actions with timestamp

saveState(label) → saves JSON snapshot of data + columns

undo() & redo() → restore previous/next state

Download

uniqueFilename(base, ext) → appends timestamp to prevent overwrite

downloadJSON() → downloads filtered data as JSON

downloadExcel() → downloads filtered data as Excel (xlsx)

📌 APIs / Libraries Used

Bootstrap 5.3 (UI components, modal, buttons, grid, utilities)

Bootstrap Icons (icons for buttons: trash, plus, reload, etc.)

SheetJS (xlsx)

XLSX.read() → read Excel files

XLSX.utils.sheet_to_json() → parse Excel to JSON

XLSX.utils.json_to_sheet() → convert JSON to Excel

XLSX.utils.book_new() / book_append_sheet() / writeFile() → export Excel

Web APIs

FileReader → read uploaded files

Blob + URL.createObjectURL → download JSON

beforeunload → warn user on page reload/close

JavaScript

Array.splice, Array.filter, Array.sort for data manipulation

Date.now() + toLocaleTimeString() for unique filenames + timestamps

JSON.stringify / JSON.parse for state snapshots