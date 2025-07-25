# TypeScript Backend Template

A comprehensive, production-ready TypeScript template for building scalable Node.js backend applications. This template includes modern development tools, architectural patterns, and best practices to kickstart your backend projects.

## 🚀 Features

### Core Framework & Server
- **Express.js** setup with TypeScript support
- **REST API** structure with organized endpoints
- **Health check** endpoint (`/rest/health`)
- **CORS** middleware configuration
- **Live reload** development with `tsx --watch`

### Development Experience
- **TypeScript** configuration with strict mode
- **Module aliases** for absolute imports (`src/*`)
- **Live reload** during development
- **Hot reloading** with tsx watch mode
- **Source maps** for debugging

### Code Quality & Linting
- **ESLint** with TypeScript support
- **Prettier** integration for code formatting
- **Module boundaries** enforcement with `@j2blasco/ts-boundaries`
- **Import/export** linting rules
- **Automated boundary generation** via custom scripts

### Testing
- **Jest** test framework with TypeScript support
- **ts-jest** preset for TypeScript testing
- **ESM support** for modern JavaScript features
- **Test utilities** and setup files
- **Separate test configurations** for different test types

### Architecture & Patterns
- **Dependency Injection** system with custom injector
- **Module boundaries** for enforcing architectural constraints
- **Environment management** with different provider configurations
- **Service layer** organization
- **Clean separation** of concerns

### Environment & Configuration
- **Environment-specific** provider registration
- **System environment** management
- **Multiple environment** support (alpha, beta, prod, test)
- **Environment variable** handling

### Build & Scripts
- **Build** system with TypeScript compiler
- **Custom scripts** with separate TypeScript configuration
- **Automated boundary** generation
- **Script utilities** for project maintenance

## 📁 Project Structure

```
typescript-backend-template/
├── src/
│   ├── index.ts                    # Application entry point
│   ├── module-alias.ts            # Module alias configuration
│   ├── api/
│   │   └── rest/                  # REST API implementation
│   │       ├── rest-server.ts     # Express server setup
│   │       ├── endpoints/         # API endpoints
│   │       └── utils/             # API utilities (CORS, etc.)
│   ├── common/                    # Shared utilities and domain logic
│   ├── environment/               # Environment management
│   │   ├── env/                   # Environment utilities
│   │   └── providers/             # Environment-specific providers
│   ├── services/
│   │   └── injector/              # Dependency injection system
│   └── testing/                   # Test utilities
├── scripts/                       # Build and maintenance scripts
├── eslint.config.mjs             # ESLint configuration
├── jest.config.ts                # Jest testing configuration
├── tsconfig.json                 # TypeScript configuration
└── package.json                  # Dependencies and scripts
```

## 🛠️ Getting Started

### Prerequisites
- Node.js (v18+ recommended)
- npm or yarn

### Installation

1. **Clone the template:**
   ```bash
   git clone https://github.com/j2blasco/typescript-backend-template.git
   cd typescript-backend-template
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start development server:**
   ```bash
   npm run dev
   ```

The server will start at `http://localhost:4001` with live reload enabled.

## 📜 Available Scripts

- **`npm run dev`** - Start development server with live reload
- **`npm run build`** - Build the project for production
- **`npm start`** - Start the production server
- **`npm run lint`** - Run ESLint and check module boundaries
- **`npm run lint:fix`** - Fix linting issues automatically
- **`npm test`** - Run Jest tests
- **`npm run boundaries`** - Generate module boundary configurations
- **`npm run script`** - Run custom scripts with TypeScript support

## 🏗️ Key Features Explained

### Module Aliases
The template uses module aliases to enable absolute imports:
```typescript
// Instead of relative imports
import { something } from '../../../common/domain-list';

// Use absolute imports
import { something } from 'src/common/domain-list';
```

### Module Boundaries
Enforces architectural constraints by defining which modules can import from each other. Boundaries are defined in `.boundaries.ts` files and automatically generate ESLint rules.

### Dependency Injection
A lightweight dependency injection system using tokens:
```typescript
const MyServiceToken = new InjectToken<MyService>('MyService');
DependencyInjector.register(MyServiceToken, new MyService());
const service = DependencyInjector.inject(MyServiceToken);
```

### Environment Management
Support for multiple environments with automatic provider registration:
```typescript
await setEnvironment('prod'); // or 'alpha', 'beta', 'test'
```

### Live Reload
Development server automatically reloads when you make changes to TypeScript files, providing a smooth development experience.

## 🧪 Testing

The template includes a comprehensive testing setup:
- Jest with TypeScript support
- Separate test configurations for different types of tests
- Test utilities and setup files
- ESM support for modern testing patterns

Run tests with:
```bash
npm test
```

## 🔧 Configuration

### TypeScript
- Strict mode enabled
- Source maps for debugging
- Module resolution configured for Node.js
- Path mapping for absolute imports

### ESLint
- TypeScript-specific rules
- Import/export validation
- Prettier integration
- Module boundary enforcement

### Jest
- TypeScript preset
- ESM support
- Verbose output
- Source map support

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests and linting
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Built with modern TypeScript best practices
- Includes custom tooling for module boundaries
- Designed for scalability and maintainability

