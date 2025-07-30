# TeamSpace

A comprehensive **Next.js SaaS boilerplate** with built-in multi-tenancy, authentication, and Role-Based Access Control (RBAC). Perfect for building team collaboration platforms, project management tools, or any multi-organizational SaaS application.

## Table of Contents

- [TeamSpace](#teamspace)
  - [Table of Contents](#table-of-contents)
  - [✨ Features](#-features)
    - [🔐 Authentication](#-authentication)
    - [🏢 Organizations](#-organizations)
    - [📨 Team Invitations](#-team-invitations)
    - [👥 Member Management](#-member-management)
    - [📁 Project Management](#-project-management)
    - [💰 Billing Integration](#-billing-integration)
  - [🛡️ Role-Based Access Control (RBAC)](#️-role-based-access-control-rbac)
    - [Available Roles](#available-roles)
    - [Permissions Matrix](#permissions-matrix)
  - [🚀 Quick Start](#-quick-start)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
  - [🤝 Contributing](#-contributing)
  - [📄 License](#-license)

## ✨ Features

### 🔐 Authentication

- **Email & Password** authentication
- **GitHub OAuth** integration
- **Password recovery** via email
- **User registration** with email verification

### 🏢 Organizations

- **Multi-tenant architecture** with organization isolation
- **Create and manage** organizations
- **Organization settings** and configuration
- **Ownership transfer** capabilities
- **Organization shutdown** with data cleanup

### 📨 Team Invitations

- **Invite members** via email with role assignment
- **Pending invitation** management
- **Accept/decline** invitation workflow
- **Bulk invitation** support

### 👥 Member Management

- **Role-based member** listing and management
- **Dynamic role assignment** and updates
- **Member activity** tracking
- **Permission-based** UI rendering

### 📁 Project Management

- **Organization-scoped** project creation
- **Project metadata** management (name, URL, description)
- **Project ownership** and collaboration
- **Bulk project** operations

### 💰 Billing Integration

- **Usage-based billing** ($20/project, $10/member)
- **Billing role** separation
- **Invoice generation** and export
- **Payment tracking** and reporting

## 🛡️ Role-Based Access Control (RBAC)

### Available Roles

| Role              | Description              | Scope                        |
| ----------------- | ------------------------ | ---------------------------- |
| **Administrator** | Management permissions   | Organization-wide            |
| **Member**        | Standard user access     | Limited to assigned projects |
| **Billing**       | Financial oversight only | Billing and invoicing        |

### Permissions Matrix

|                     | Owner | Admin | Member | Billing | Anonymous |
| ------------------- | ----- | ----- | ------ | ------- | --------- |
| Update organization | ✅    | ✅    | ❌     | ❌      | ❌        |
| Delete organization | ✅    | ✅    | ❌     | ❌      | ❌        |
| Invite members      | ✅    | ✅    | ❌     | ❌      | ❌        |
| Revoke invitations  | ✅    | ✅    | ❌     | ❌      | ❌        |
| List members        | ✅    | ✅    | ✅     | ✅      | ❌        |
| Transfer ownership  | ✅    | ❌    | ❌     | ❌      | ❌        |
| Update member roles | ✅    | ✅    | ❌     | ❌      | ❌        |
| Remove members      | ✅    | ✅    | ⚠️\*   | ❌      | ❌        |
| List projects       | ✅    | ✅    | ✅     | ✅      | ❌        |
| Create projects     | ✅    | ✅    | ✅     | ❌      | ❌        |
| Update projects     | ✅    | ✅    | ⚠️\*   | ❌      | ❌        |
| Delete projects     | ✅    | ✅    | ⚠️\*   | ❌      | ❌        |
| View billing        | ✅    | ✅    | ❌     | ✅      | ❌        |
| Export billing      | ✅    | ✅    | ❌     | ✅      | ❌        |

> **Legend:** ✅ Allowed | ❌ Not allowed | ⚠️ Conditional access
>
> **\*Conditions:**
>
> - Members can only leave their own organization
> - Project updates/deletion limited to project authors
> - Ownership transfer restricted to current owners only

## 🚀 Quick Start

### Prerequisites

- **Node.js** 18+ and pnpm
- **PostgreSQL** database
- **Docker**

### Installation

```bash
# Clone the repository
git clone git@github.com:wolney-fo/teamspace.git
cd teamspace

# Install dependencies
pnpm install

# Set up environment variables
cp .env.example .env.local
# Edit .env.local with your configuration

# Start development server
pnpm run dev
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.
