# FinLocker Microservices Documentation Portal

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen)](https://tonistarq.github.io/)
[![Documentation](https://img.shields.io/badge/Documentation-DocFX-blue)](https://dotnet.github.io/docfx/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 🏗️ Overview

This repository hosts the **FinLocker Microservices Documentation Portal**, a centralized hub for all microservice API documentation. The portal provides a modern, developer-friendly landing page that showcases each microservice with direct links to their comprehensive DocFX-generated documentation.

## 🌐 Live Site

Visit the documentation portal at: **[https://tonistarq.github.io/](https://tonistarq.github.io/)**

## 📁 Repository Structure

```
tonistarq.github.io/
├── README.md                    # This file
├── index.html                   # Landing page (microservices portal)
├── favicon.ico                  # Site favicon
├── logo.svg                     # FinLocker logo
├── manifest.json               # Web app manifest
├── FinLocker.Analytics/        # Analytics microservice documentation
│   ├── index.html              # Service-specific landing page
│   ├── api/                    # Generated API documentation
│   └── ...                     # Other DocFX files
└── FinLocker.GenAI/           # GenAI microservice documentation
    ├── index.html              # Service-specific landing page
    ├── api/                    # Generated API documentation
    └── ...                     # Other DocFX files
```

## 🚀 Features

- **Modern Landing Page**: Beautiful, responsive design built with Tailwind CSS
- **Microservice Cards**: Each service displayed with descriptions, features, and tech stack
- **Developer-Focused**: Designed for developers and QA teams
- **DocFX Integration**: Seamless integration with DocFX-generated documentation
- **GitHub Pages Ready**: Optimized for GitHub Pages hosting
- **Mobile Responsive**: Works perfectly on all devices

## 📋 How to Add a New Microservice

Follow these steps to add a new microservice to the documentation portal:

### Step 1: Add Your DocFX Documentation

1. Create a `YourService.DocFx` pipeline in Azure DevOps for your repo. We have examples in `FinLocker.GenAI repo` for reference.
2. Run the pipeline to generate the DocFX documentation for your microservice.
3. This will create a folder structure similar to `FinLocker.YourService/` with an `index.html` and `api/` folder.

### Step 2: Update the Landing Page

Edit the `index.html` file and add a new service card in the services section. Find the `<!-- Services Section -->` and add your card after the existing ones:

```html
<!-- Your New Service -->
<div class="service-card bg-white rounded-lg p-8 shadow-lg">
    <div class="flex items-center mb-6">
        <div class="flex-shrink-0">
            <div class="flex items-center justify-center h-12 w-12 rounded-md bg-gradient-to-r from-[COLOR1] to-[COLOR2] text-white">
                <i class="fas fa-[ICON] text-xl"></i>
            </div>
        </div>
        <div class="ml-4">
            <h3 class="text-xl font-bold text-gray-900">[Service Name]</h3>
            <p class="text-sm text-gray-500">[Service Tagline]</p>
        </div>
    </div>
    
    <p class="text-gray-600 mb-6">
        [Detailed description of what your service does]
    </p>
    
    <div class="mb-6">
        <h4 class="text-sm font-semibold text-gray-900 mb-3">Key Features</h4>
        <div class="flex flex-wrap gap-2">
            <span class="px-3 py-1 bg-[COLOR]-100 text-[COLOR]-800 text-xs rounded-full">🔧 [Feature 1]</span>
            <span class="px-3 py-1 bg-[COLOR]-100 text-[COLOR]-800 text-xs rounded-full">⚡ [Feature 2]</span>
            <span class="px-3 py-1 bg-[COLOR]-100 text-[COLOR]-800 text-xs rounded-full">🔒 [Feature 3]</span>
        </div>
    </div>
    
    <div class="mb-6">
        <h4 class="text-sm font-semibold text-gray-900 mb-3">Technologies</h4>
        <div class="flex flex-wrap gap-2">
            <span class="tech-badge text-white px-2 py-1 text-xs rounded">[Tech 1]</span>
            <span class="tech-badge text-white px-2 py-1 text-xs rounded">[Tech 2]</span>
            <span class="tech-badge text-white px-2 py-1 text-xs rounded">[Tech 3]</span>
        </div>
    </div>
    
    <div class="flex space-x-3">
        <a href="[YourServiceFolder]/" class="flex-1 bg-[COLOR]-600 text-white text-center py-2 px-4 rounded-md hover:bg-[COLOR]-700 transition duration-150 ease-in-out">
            <i class="fas fa-book mr-2"></i>View Documentation
        </a>
    </div>
</div>
```

### Step 3: Customize Your Service Card

Replace the placeholders with your service information:

| Placeholder | Description | Example |
|-------------|-------------|---------|
| `[COLOR1]` & `[COLOR2]` | Gradient colors for icon background | `green-500` & `green-600` |
| `[ICON]` | FontAwesome icon name | `shield-alt`, `cog`, `database` |
| `[Service Name]` | Your service display name | `Authentication Service` |
| `[Service Tagline]` | Brief service description | `Security & Identity Management` |
| `[Detailed description]` | What your service does | `Handles user authentication, authorization...` |
| `[Feature X]` | Key features of your service | `OAuth 2.0 Support`, `Role-Based Access` |
| `[COLOR]` | Color theme for badges | `green`, `blue`, `purple` |
| `[Tech X]` | Technologies used | `.NET 8.0`, `Redis`, `JWT` |
| `[YourServiceFolder]` | Your documentation folder name | `FinLocker.Auth` |

### Step 4: Update Grid Layout (if needed)

If adding more than 2 services, consider updating the grid layout in the services section:

```html
<!-- For 3 services, change from: -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-8">

<!-- To: -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
```

## 🎨 Design Guidelines

### Color Schemes
Choose complementary colors for your service card:
- **Blue Theme**: `blue-500` to `blue-600` (Analytics/Data services)
- **Purple Theme**: `purple-500` to `pink-600` (AI/ML services)
- **Green Theme**: `green-500` to `green-600` (Security/Auth services)
- **Orange Theme**: `orange-500` to `red-600` (API Gateway/Communication)
- **Indigo Theme**: `indigo-500` to `indigo-600` (Core Platform services)

### Icons
Use FontAwesome icons that represent your service:
- 🔒 Security: `shield-alt`, `lock`, `key`
- 📊 Analytics: `chart-line`, `chart-bar`, `analytics`
- 🤖 AI/ML: `brain`, `robot`, `magic`
- 🔧 Tools: `cog`, `wrench`, `tools`
- 📡 API: `server`, `network-wired`, `cloud`
- 💾 Database: `database`, `hdd`, `archive`

### Feature Badges
Use appropriate emojis and colors for feature badges:
- Security: 🔒🛡️⚡ with `green` colors
- Performance: ⚡🚀💪 with `blue` colors  
- AI/ML: 🤖🧠🎯 with `purple` colors
- Analytics: 📊📈🔍 with `indigo` colors

## 🔧 Local Development

To work on the landing page locally:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/tonistarq/tonistarq.github.io.git
   cd tonistarq.github.io
   ```

2. **Serve locally** (using Python):
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Or Python 2
   python -M SimpleHTTPServer 8000
   ```

3. **Open in browser**:
   Navigate to `http://localhost:8000`

## 🚀 Deployment

The site is automatically deployed via **GitHub Pages** when changes are pushed to the `main` branch. No additional configuration required!

## 📝 Contributing

1. Fork the repository
2. Create a feature branch
3. Add your microservice documentation
4. Update the landing page following the guide above
5. Test locally
6. Submit a pull request

## 🛠️ Technologies Used

- **Frontend**: HTML5, Tailwind CSS, FontAwesome
- **Documentation**: DocFX
- **Hosting**: GitHub Pages
- **CI/CD**: GitHub Actions (automatic deployment)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Support

For questions or support:
- 📧 Contact the development team
- 🐛 [Report issues](https://github.com/tonistarq/tonistarq.github.io/issues)
- 📖 [View documentation](https://tonistarq.github.io/)

---

**Built with ❤️ by the FinLocker Team** | Powered by [DocFX](https://dotnet.github.io/docfx/) and [GitHub Pages](https://pages.github.com/)
