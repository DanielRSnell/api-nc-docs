# Nightcrawler Dashboard

A modern Single Page Application (SPA) for the Nightcrawler Dashboard built with Astro and React.

## Project Overview

Nightcrawler Dashboard is a comprehensive management interface designed to provide intuitive access to pools, teams, silicon resources, workflows, and system settings. The application is built as a SPA using modern web technologies to ensure optimal performance and user experience.

## Tech Stack

### Frontend

- **Framework**: [Astro](https://astro.build/) with [React](https://reactjs.org/)
- **UI Components**: [ShadCN](https://ui.shadcn.com/) - Beautifully designed components built with Radix UI and Tailwind CSS
- **Styling**: [Tailwind CSS v4](https://tailwindcss.com/) - Utility-first CSS framework
- **State Management**: [Zustand](https://github.com/pmndrs/zustand) - A small, fast and scalable state-management solution
- **Data Persistence**: Local Storage caching for client-side data persistence
- **Authentication**: [Keycloak](https://www.keycloak.org/) - Open Source Identity and Access Management

### Development Tools

- **Package Manager**: [pnpm](https://pnpm.io/) - Fast, disk space efficient package manager

## Features

The Nightcrawler Dashboard includes the following key features:

- **Main Dashboard**: Overview of system status and key metrics
- **Pools Management**: Create, monitor, and manage resource pools
- **Team Management**: Organize and manage team members and permissions
- **Silicon Resources**: Track and allocate silicon resources
- **Workflow Management**: Design, implement, and monitor workflows
- **Settings**: Configure system and user preferences
- **Authentication**: Secure login and user management via Keycloak

## Getting Started

### Prerequisites

- Node.js (v18 or later)
- pnpm (v8 or later)

### Installation

```bash
# Clone the repository
git clone [repository-url]
cd nightcrawler-dashboard

# Install dependencies
pnpm install

# Create environment file
cp .env.example .env
# Update the .env file with your configuration

# Start the development server
pnpm dev
```

### Building for Production

```bash
# Build the application
pnpm build

# Preview the production build
pnpm preview
```

## Backend Integration TODO

Based on the API documentation tasks in [tasks.md](/tasks.md), the following backend integrations have been documented and need to be implemented:

- **Dashboard API**: Integration with backend services for dashboard metrics and data visualization
- **Pools API**: Backend services for managing resource pools
- **Authentication API**: Keycloak integration for secure authentication
- **Settings API**: Backend services for system configuration
- **Teams API**: Services for team management and permissions
- **Silicon API**: Backend for silicon resource allocation and tracking
- **Workflow API**: Services for workflow design, execution, and monitoring

All API documentation has been completed for these components and can be found in the `/docs/api/` directory.

## Project Structure

```
nightcrawler-dashboard/
├── public/              # Static assets
├── src/
│   ├── components/      # Reusable UI components
│   ├── layouts/         # Page layouts
│   ├── lib/             # Utility functions and hooks
│   ├── pages/           # Astro pages
│   ├── stores/          # Zustand state stores
│   └── styles/          # Global styles
├── docs/
│   └── api/             # API documentation
├── .env.example         # Example environment variables
├── astro.config.mjs     # Astro configuration
├── tailwind.config.js   # Tailwind CSS configuration
└── README.md            # Project documentation
```
