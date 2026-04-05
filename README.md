# Finance Dashboard

A modern, responsive finance dashboard application built with React, TypeScript, and Vite. Track your financial activity with an intuitive interface featuring transaction management, analytics, and role-based access control.

## Features

### 📊 Dashboard Overview
- **Summary Cards**: Display Total Balance, Total Income, and Total Expenses
- **Visual Analytics**: 
  - Monthly Balance Trend (Line Chart)
  - Spending by Category (Bar Chart)
  - Expense Distribution (Pie Chart)
- **Key Insights**:
  - Highest Spending Category
  - Monthly Expense Trends
  - Savings Rate Calculation

### 💳 Transactions Management
- **View Transactions**: Browse detailed transaction history
- **Advanced Filtering**:
  - Filter by Category
  - Filter by Type (Income/Expense)
  - Search by Description or Category
- **Sorting Options**:
  - Sort by Date or Amount
  - Ascending/Descending Order
- **Role-Based Actions**:
  - **Viewer**: Read-only access to all data
  - **Admin**: Can add, edit, and delete transactions

### 🔐 Role-Based UI
- **Viewer Role**: Can only view financial data and insights
- **Admin Role**: Can:
  - Add new transactions via inline form
  - Delete existing transactions
  - Full data access
- Easy role switching via dropdown in header

### 📱 Responsive Design
- Fully responsive layout works on:
  - Desktop screens
  - Tablets
  - Mobile devices
- Touch-friendly interface
- Optimized CSS for all screen sizes

## Tech Stack

- **Frontend Framework**: React 18.2 with TypeScript
- **Build Tool**: Vite 5
- **State Management**: React Context API
- **Charting Library**: Recharts 2.10
- **Styling**: CSS3 with modern features (Grid, Flexbox, Gradients)

## Project Structure

```
src/
├── components/
│   ├── Dashboard.tsx          # Main dashboard container
│   ├── Header.tsx             # Header with role selector
│   ├── SummaryCards.tsx       # Summary statistics cards
│   ├── Charts.tsx             # Chart visualizations
│   ├── Transactions.tsx       # Transaction list and form
│   ├── Insights.tsx           # Key insights display
│   └── *.css                  # Component styling
├── context/
│   └── DashboardContext.tsx   # Global state management
├── data/
│   └── mockData.ts            # Sample transactions data
├── utils/
│   └── calculations.ts        # Business logic utilities
├── types.ts                   # TypeScript type definitions
├── App.tsx                    # Root component
├── main.tsx                   # Entry point
└── index.css                  # Global styles
```

## Getting Started

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn

### Installation

1. Install dependencies:
```bash
npm install
```

2. Start the development server:
```bash
npm run dev
```

3. Open http://localhost:5173 in your browser

### Building for Production

```bash
npm run build
```

The optimized build will be created in the `dist/` directory.

### Preview Production Build

```bash
npm run preview
```

## Usage Guide

### Viewing Transactions
1. Scroll to the Transactions section
2. Use filters to narrow down transactions:
   - Search by description or category
   - Filter by category
   - Filter by type (income/expense)
3. Sort by date or amount with ascending/descending options

### Adding Transactions (Admin Only)
1. Click the "+ Add Transaction" button
2. Fill in the form fields:
   - Date
   - Type (Income/Expense)
   - Amount
   - Category
   - Description
3. Click "✓ Add Transaction"

### Deleting Transactions (Admin Only)
1. Navigate to the transaction row
2. Click the "🗑️ Delete" button
3. Confirm deletion when prompted

### Understanding the Analytics
- **Summary Cards**: Quick overview of financial position
- **Monthly Trend**: Line chart showing balance changes over time
- **Spending by Category**: Bar chart of expenses by category
- **Expense Distribution**: Pie chart showing proportion of spending

### Role Switching
1. Use the role selector dropdown in the header
2. Select "Viewer" for read-only access
3. Select "Admin" for editing permissions
4. UI elements will update based on selected role

## State Management

The application uses **React Context API** for state management with the following structure:

```typescript
interface DashboardState {
  transactions: Transaction[];
  userRole: UserRole;
  filters: {
    category: string | null;
    type: TransactionType | null;
    searchTerm: string;
  };
}
```

### Available Actions
- `setUserRole()`: Switch between viewer and admin roles
- `addTransaction()`: Add a new transaction
- `deleteTransaction()`: Remove a transaction
- `setFilters()`: Update filter values
- `getFilteredTransactions()`: Get transactions matching current filters

## Data Persistence

Currently, the application uses mock data loaded in memory. To add data persistence:

1. **Local Storage**: Uncomment localStorage logic in DashboardContext.tsx
2. **Backend API**: Replace mock data with API calls to a backend service
3. **IndexedDB**: Implement browser database storage for larger datasets

## Future Enhancements

- [ ] Dark mode support
- [ ] Data persistence with localStorage
- [ ] CSV/JSON export functionality
- [ ] Advanced filtering and grouping
- [ ] Budget goals and alerts
- [ ] Recurring transactions
- [ ] Multi-currency support
- [ ] Advanced analytics dashboard

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Keyboard Shortcuts

- `Escape`: Close dialogs and forms
- `Tab`: Navigate through form inputs
- `Enter`: Submit forms

## Performance Optimizations

- Lazy loading of components
- Memoized calculations
- Efficient re-renders with React hooks
- Optimized CSS with minimal repaints
- Responsive images and assets

## Contributing

Feel free to fork this project and submit pull requests for any improvements.

## License

MIT License - Feel free to use this project for personal or commercial purposes.

## Author

Created as a demonstration of modern React development practices with TypeScript, Vite, and Context API.

## Support

For issues or questions, please open an GitHub issue or contact the development team.

---

**Last Updated**: April 2026
