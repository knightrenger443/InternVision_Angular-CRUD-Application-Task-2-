# Angular CRUD Application - Product Manager

[![Angular](https://img.shields.io/badge/Angular-16-red.svg)](https://angular.io/)
[![Material UI](https://img.shields.io/badge/Material%20UI-16-blue.svg)](https://material.angular.io/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.1-blue.svg)](https://www.typescriptlang.org/)
[![SCSS](https://img.shields.io/badge/SCSS-Styled-pink.svg)](https://sass-lang.com/)

A modern, responsive Angular CRUD (Create, Read, Update, Delete) application for managing products. Built with Angular 16, Angular Material, and TypeScript, featuring a clean architecture, advanced search/filtering, and a beautiful Material Design UI.

## 🚀 Features

### Core Functionality
- ✅ **Full CRUD Operations** - Create, Read, Update, and Delete products
- ✅ **Advanced Search & Filtering** - Search by name, description, or category
- ✅ **Category Management** - Organize products by categories
- ✅ **Bulk Operations** - Select and delete multiple products at once
- ✅ **Real-time Data Updates** - Reactive forms with instant validation feedback
- ✅ **Data Persistence** - Local storage integration for data retention

### User Experience
- 🎨 **Material Design UI** - Clean, modern interface with Google Material Design
- 📱 **Fully Responsive** - Works seamlessly on desktop, tablet, and mobile devices
- ⚡ **Fast Performance** - Optimized with OnPush change detection and lazy loading
- 🔍 **Advanced Table Features** - Sorting, pagination, and selection
- 💫 **Smooth Animations** - Loading states and transitions
- 📝 **Form Validation** - Comprehensive validation with custom validators

### Technical Features
- 🏗️ **Clean Architecture** - Feature modules, services, and shared components
- 🛡️ **Type Safety** - Full TypeScript implementation with strict typing
- 🎯 **Custom Validators** - Business-specific validation rules
- 📊 **State Management** - RxJS and BehaviorSubjects for state handling
- 🎨 **SCSS Styling** - Modular styles with Material theming
- 📱 **PWA Ready** - Prepared for Progressive Web App features

## 🖼️ Screenshots

### Product List View
![Product List](docs/images/product-list.png)

### Create/Edit Product Form
![Product Form](docs/images/product-form.png)

### Mobile Responsive Design
![Mobile View](docs/images/mobile-view.png)

## 🏗️ Architecture

```
src/
├── app/
│   ├── core/                    # Core services and guards
│   │   └── services/
│   │       └── product.service.ts
│   ├── features/                # Feature modules
│   │   └── products/
│   │       ├── components/
│   │       │   ├── product-list/
│   │       │   ├── product-create/
│   │       │   └── product-edit/
│   │       ├── products.module.ts
│   │       └── products-routing.module.ts
│   ├── shared/                  # Shared components and utilities
│   │   ├── components/
│   │   │   └── navbar/
│   │   ├── models/
│   │   │   └── product.model.ts
│   │   ├── validators/
│   │   │   └── product.validators.ts
│   │   └── material.module.ts
│   ├── app-routing.module.ts
│   ├── app.component.ts
│   └── app.module.ts
├── styles/
│   └── styles.scss              # Global styles and Material theming
└── assets/                      # Static assets
```

## 📦 Tech Stack

- **Framework**: Angular 16
- **UI Library**: Angular Material 16
- **Language**: TypeScript 5.1
- **Styling**: SCSS with Material theming
- **State Management**: RxJS & BehaviorSubjects
- **Forms**: Reactive Forms with custom validators
- **Build Tool**: Angular CLI
- **Package Manager**: npm

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:
- Node.js (version 16 or higher)
- npm (comes with Node.js)
- Angular CLI (optional but recommended)

```bash
# Check Node.js version
node --version

# Check npm version
npm --version

# Install Angular CLI globally (optional)
npm install -g @angular/cli
```

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd angular-crud-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm start
   # or
   ng serve
   ```

4. **Open your browser**
   Navigate to `http://localhost:4200/`

## 📋 Available Scripts

| Script | Description |
|--------|-------------|
| `npm start` | Start development server on port 4200 |
| `npm run build` | Build the app for production |
| `npm run build:prod` | Build with production optimizations |
| `npm test` | Run unit tests with Karma |
| `npm run e2e` | Run end-to-end tests |
| `npm run lint` | Run ESLint for code quality |
| `npm run serve` | Serve built application locally |

## 🎯 Usage Guide

### Managing Products

#### Adding a New Product
1. Click the "Add Product" button in the top navigation or product list
2. Fill in the required fields:
   - **Product Name**: Must be 2-100 characters, alphanumeric
   - **Price**: Must be greater than ₹0.01
   - **Description**: Minimum 10 characters, maximum 1000
   - **Category**: Select from predefined categories
   - **Stock Quantity**: Must be between 0-10,000
   - **Image URL**: Optional, must be a valid URL if provided
3. Click "Create Product" to save

#### Editing Products
1. In the product list, click the edit (pencil) icon for any product
2. Modify the fields as needed
3. Click "Update Product" to save changes

#### Deleting Products
- **Single Delete**: Click the delete (trash) icon for individual products
- **Bulk Delete**: Select multiple products using checkboxes and click "Delete Selected"

#### Search and Filter
- **Search**: Type in the search box to find products by name, description, or category
- **Category Filter**: Use the dropdown to filter by specific categories
- **Clear Filters**: Click "Clear Filters" to reset all filters

#### Table Features
- **Sorting**: Click column headers to sort (Name, Category, Price, Stock)
- **Pagination**: Use pagination controls at the bottom of the table
- **Selection**: Click checkboxes to select products for bulk operations

## 🔧 Configuration

### Environment Configuration

The app supports different environment configurations:

```typescript
// src/environments/environment.ts
export const environment = {
  production: false,
  apiUrl: 'http://localhost:3000/api', // For future API integration
  storageKey: 'angular-crud-products'
};
```

### Material Theme Customization

Customize the Material theme in `src/styles/styles.scss`:

```scss
// Define custom color palette
$primary: mat.define-palette(mat.$indigo-palette, 500);
$accent: mat.define-palette(mat.$pink-palette, A200, A100, A400);
$warn: mat.define-palette(mat.$red-palette);
```

## 🧪 Testing

### Running Unit Tests
```bash
npm test
```

### Running E2E Tests
```bash
npm run e2e
```

### Test Coverage
```bash
npm run test:coverage
```

## 🔄 Data Management

### Local Storage

The application uses browser localStorage to persist data:
- **Key**: `angular-crud-products`
- **Data**: JSON array of product objects
- **Automatic Backup**: Data is automatically saved on every change

### Default Data

If no data exists in localStorage, the app initializes with sample products:
- MacBook Pro 16"
- iPhone 15 Pro
- Wireless Headphones

### Data Export/Import (Future Enhancement)

Planned features:
- Export products to JSON/CSV
- Import products from file
- Data backup and restore

## 🎨 Customization

### Adding New Product Fields

1. **Update the model** in `src/app/shared/models/product.model.ts`
2. **Add validators** in `src/app/shared/validators/product.validators.ts`
3. **Update forms** in create and edit components
4. **Update templates** to display new fields
5. **Update table columns** in the product list component

### Adding New Categories

Modify the categories array in `product.service.ts`:

```typescript
private readonly categories = [
  'Electronics', 'Clothing', 'Books', 'Home & Garden', 
  'Sports', 'Toys', 'Your New Category'
];
```

### Custom Validators

Add new validators in `src/app/shared/validators/product.validators.ts`:

```typescript
static customValidator(): ValidatorFn {
  return (control: AbstractControl): ValidationErrors | null => {
    // Your validation logic here
    return null;
  };
}
```

## 🚀 Deployment

### Build for Production

```bash
npm run build
```

This creates a `dist/` folder with optimized production files.

### Deployment Options

1. **Static Hosting** (Netlify, Vercel, GitHub Pages)
2. **Cloud Platforms** (AWS S3, Google Cloud Storage)
3. **Traditional Web Servers** (Apache, Nginx)
4. **Docker Containers**

### Docker Deployment

```dockerfile
FROM node:16-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist/angular-crud-app /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

## 🛠️ Development

### Code Style

The project follows Angular style guide:
- **Linting**: ESLint with Angular rules
- **Formatting**: Prettier
- **Naming**: PascalCase for classes, camelCase for variables
- **File Organization**: Feature-based module structure

### Git Workflow

1. Create feature branch: `git checkout -b feature/your-feature`
2. Make changes and commit: `git commit -m "Add your feature"`
3. Push to branch: `git push origin feature/your-feature`
4. Create Pull Request

### Performance Tips

- Use OnPush change detection strategy
- Implement virtual scrolling for large lists
- Optimize images and assets
- Use lazy loading for routes
- Minimize bundle size with tree shaking

## 🤝 Contributing

1. **Fork the repository**
2. **Create your feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

### Development Guidelines

- Write meaningful commit messages
- Add unit tests for new features
- Update documentation as needed
- Follow the existing code style
- Test on multiple devices/browsers

## 🚧 Roadmap

### Planned Features

- [ ] **API Integration** - Connect to REST/GraphQL backend
- [ ] **Authentication** - User login and role-based access
- [ ] **Advanced Analytics** - Product performance metrics
- [ ] **Image Upload** - Direct image upload functionality
- [ ] **Export/Import** - Data export in multiple formats
- [ ] **Dark Mode** - Theme switching capability
- [ ] **Offline Support** - PWA with offline functionality
- [ ] **Real-time Updates** - WebSocket integration
- [ ] **Advanced Filters** - Date ranges, price ranges
- [ ] **Barcode Scanning** - Product identification

### Version History

- **v1.0.0** - Initial release with basic CRUD
- **v1.1.0** - Added Material UI and responsive design
- **v1.2.0** - Enhanced search, filtering, and validation
- **v1.3.0** - Bulk operations and advanced table features

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- LinkedIn: [Your LinkedIn](https://linkedin.com/in/yourprofile)
- Email: your.email@example.com

## 🙏 Acknowledgments

- [Angular Team](https://angular.io) for the amazing framework
- [Material Design](https://material.io) for the design system
- [RxJS](https://rxjs.dev) for reactive programming
- Community contributors and feedback

---

**⭐ Star this repository if you found it helpful!**

For questions, suggestions, or support, please open an issue or reach out directly.