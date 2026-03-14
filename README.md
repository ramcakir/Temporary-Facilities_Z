# Temporary Facilities Cost Estimator

A Progressive Web Application (PWA) for calculating temporary facilities costs for large construction projects. Built with Next.js 16, TypeScript, and Tailwind CSS.

## Features

### Cost Categories

The estimator covers all major temporary facilities cost categories:

1. **Mobilisation & Demobilisation**
   - Initial site setup
   - Site clearance and demobilisation
   - Crane mobilisation
   - Transport costs

2. **Temporary Buildings**
   - Site offices (calculated by m² per staff member)
   - Meeting rooms
   - Storage containers
   - Staff canteen

3. **Temporary Foundations**
   - Building foundations
   - Site roadways
   - Hardstanding areas

4. **Facilities & Utilities**
   - Air conditioning units
   - Heating systems
   - Electricity connection
   - Water connection
   - Internet/communications

5. **Sanitary & Kitchen Facilities**
   - Portable toilets
   - Flush toilets
   - Kitchen facilities
   - Drinking water stations

6. **Services**
   - Cleaning services
   - Waste disposal
   - Security services
   - Maintenance

### Pricing Options

Two pricing models are available for comparison:

- **Rent Option**: Monthly rental costs plus one-time setup fees
- **Buy Option**: Purchase equipment and facilities outright

The application provides a recommendation based on which option is more cost-effective for your project duration.

### Pricing Level

All default rates are based on **Dutch/Western Europe 2024-2025** price levels:

- Prices in EUR (€)
- Based on current market rates in the Netherlands and surrounding regions
- Includes realistic purchase-to-rental multipliers

### Editable Parameters

All parameters are fully editable:

**Project Parameters:**
- Project name
- Project duration (months)
- Site area (m²)
- Number of staff
- Number of meeting rooms
- Number of toilets
- Number of kitchens
- Cleaning frequency

**Unit Rates:**
- All rental rates (per unit per month)
- All purchase prices
- One-time costs (connections, mobilisation)
- Purchase price multipliers

## Installation

### Prerequisites

- Node.js 18+ or Bun
- Modern web browser with PWA support

### Local Development

```bash
# Install dependencies
bun install

# Run development server
bun run dev
```

The application will be available at `http://localhost:3000`

### Production Build

```bash
# Build for production
bun run build

# Start production server
bun run start
```

## PWA Features

This application is a fully-featured Progressive Web App:

### Offline Support

- Service worker caches all static assets
- Application works offline after first load
- Data is saved to localStorage automatically

### Install on Device

The app can be installed on:

- **Desktop**: Chrome, Edge, Safari
- **Mobile**: iOS Safari, Android Chrome
- **Tablets**: iPad, Android tablets

To install:
1. Visit the application in a supported browser
2. Look for the "Install" prompt in the address bar
3. Click "Install" to add to home screen/desktop

### App Icons

Icons are provided in multiple sizes for various devices:
- 72x72, 96x96, 128x128, 144x144, 152x152, 192x192, 384x384, 512x512

## Usage Guide

### Quick Start

1. **Overview Tab**: View cost summary and rent vs buy comparison
2. **Project Tab**: Enter project parameters
3. **Unit Rates Tab**: Adjust unit rates as needed
4. **Details Tab**: View detailed cost breakdown

### Export Options

- **CSV Export**: Download spreadsheet for further analysis
- **JSON Export**: Full data export including all parameters
- **Print**: Browser print functionality for reports

### Saving Data

- Click "Save" to save to browser localStorage
- Data persists between sessions
- Use "Reset" to restore default values

## File Structure

```
/
├── public/
│   ├── manifest.json      # PWA manifest
│   ├── sw.js              # Service worker
│   └── icons/             # App icons in various sizes
│       ├── icon-72x72.png
│       ├── icon-96x96.png
│       ├── icon-128x128.png
│       ├── icon-144x144.png
│       ├── icon-152x152.png
│       ├── icon-192x192.png
│       ├── icon-384x384.png
│       └── icon-512x512.png
├── src/
│   ├── app/
│   │   ├── layout.tsx     # Root layout with PWA meta tags
│   │   ├── page.tsx       # Main application
│   │   └── globals.css    # Global styles
│   ├── components/ui/     # shadcn/ui components
│   └── hooks/             # Custom React hooks
└── README.md
```

## Technology Stack

- **Framework**: Next.js 16 with App Router
- **Language**: TypeScript 5
- **Styling**: Tailwind CSS 4
- **UI Components**: shadcn/ui (New York style)
- **Icons**: Lucide React
- **PWA**: Service Worker, Web App Manifest

## Default Unit Rates (2024-2025 Dutch Prices)

### Mobilisation
| Item | Rate |
|------|------|
| Setup (lump sum) | €25,000 |
| Demobilisation (lump sum) | €18,000 |
| Transport per km | €15 |
| Crane mobilisation | €8,500 |

### Temporary Buildings (per month)
| Item | Rate |
|------|------|
| Office space | €45/m² |
| Meeting room | €1,200/room |
| Storage container | €350/container |
| Canteen | €55/m² |

### Foundations (one-time)
| Item | Rate |
|------|------|
| Temporary foundation | €85/m² |
| Site roadways | €65/m² |
| Hardstanding | €45/m² |

### Facilities
| Item | Rate |
|------|------|
| Air conditioning | €450/unit/month |
| Heating | €380/unit/month |
| Electricity connection | €15,000 (lump sum) |
| Water connection | €8,500 (lump sum) |
| Internet | €250/month |

### Sanitary (per month)
| Item | Rate |
|------|------|
| Portable toilet | €185/unit |
| Flush toilet | €450/unit |
| Kitchen facility | €950/unit |
| Drinking water station | €120/unit |

### Services
| Item | Rate |
|------|------|
| Cleaning | €285/visit |
| Waste disposal | €1,250/month |
| Security guard | €4,500/month |
| Maintenance | €1,850/month |

### Purchase Multipliers
| Category | Years of Rent = Purchase Price |
|----------|-------------------------------|
| Buildings | 5 years |
| Facilities | 4 years |
| Equipment | 3 years |

## Calculation Methodology

### Quantities

Quantities are automatically calculated based on project parameters:

- **Office area**: 8 m² per staff member
- **Canteen area**: 1.5 m² per staff member
- **Storage containers**: 1 per 500 m² site area
- **AC units**: 1 per 50 m² building area
- **Heating units**: 1 per 80 m² building area
- **Portable toilets**: 60% of total toilets
- **Flush toilets**: 40% of total toilets
- **Drinking water stations**: 1 per 30 staff
- **Security guards**: 1 per 2,500 m² site area
- **Site roadways**: 15% of site area
- **Hardstanding**: 10% of site area

### Rent vs Buy Comparison

- **Rent**: Monthly costs × duration + one-time setup costs
- **Buy**: All purchase prices (with potential residual value of 30%)

## Browser Support

- Chrome 80+
- Firefox 78+
- Safari 14+
- Edge 80+

## License

MIT License - Free to use and modify.

## Contributing

Contributions are welcome! Please submit issues and pull requests.

## Changelog

### v1.0.0 (2024)
- Initial release
- Full PWA support
- All cost categories implemented
- Rent vs buy comparison
- Editable unit rates
- Export functionality
