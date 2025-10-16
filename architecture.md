# SDG 8: AI Business Insight Module - Architecture

## Overview
A Flutter app that helps small businesses make data-driven decisions for growth and decent work using AI clustering and analytics.

## Core Features (MVP)
1. **Dashboard**: Overview of business clusters and key metrics
2. **Business Data Input**: Add/edit business data (employment rate, productivity, revenue, firm size)
3. **AI Clustering**: K-Means clustering to group similar businesses
4. **Visualization**: Interactive charts showing cluster distributions and performance
5. **Insights**: Actionable recommendations based on cluster analysis
6. **Business List**: View all businesses with their cluster assignments

## Technical Stack
- **State Management**: StatefulWidget with local state
- **Data Storage**: Local storage using shared_preferences
- **Visualization**: fl_chart for interactive charts
- **UI**: Custom modern design with gradient backgrounds and glassmorphism effects

## Project Structure

### Data Models (`lib/models/`)
1. **business.dart**: Business entity with metrics (employment_rate, productivity, revenue, firm_size, cluster)
2. **cluster_result.dart**: Cluster analysis results with statistics and insights

### Services (`lib/services/`)
1. **business_service.dart**: CRUD operations for businesses, local storage management
2. **clustering_service.dart**: K-Means clustering algorithm implementation, silhouette score calculation

### Screens (`lib/screens/`)
1. **home_screen.dart**: Main dashboard with cluster overview and quick stats
2. **business_list_screen.dart**: List of all businesses with filtering by cluster
3. **add_business_screen.dart**: Form to add/edit business data
4. **insights_screen.dart**: Detailed cluster analysis with visualizations and recommendations

### Widgets (`lib/widgets/`)
1. **cluster_card.dart**: Display cluster statistics
2. **business_card.dart**: Display individual business info
3. **metric_chart.dart**: Reusable chart widget for various metrics
4. **gradient_container.dart**: Custom gradient background container

## Data Model Details

### Business
- id: String
- name: String
- employmentRate: double (0-100)
- productivity: double (arbitrary positive value)
- revenue: double (in thousands)
- firmSize: int (number of employees)
- cluster: int? (0, 1, 2)
- createdAt: DateTime
- updatedAt: DateTime

### ClusterResult
- clusterStats: Map<int, Map<String, double>> (mean values per cluster)
- silhouetteScore: double
- totalBusinesses: int
- clusterCounts: Map<int, int>
- recommendations: Map<int, String>

## Color Palette (Modern & Vibrant)
- Primary: Deep teal (#00897B)
- Secondary: Bright coral (#FF6F61)
- Accent: Golden yellow (#FFD54F)
- Background gradients: Soft blues and purples
- Cluster colors: Emerald green, Azure blue, Sunset orange

## Implementation Steps
1. Set up dependencies (fl_chart, shared_preferences)
2. Create data models with JSON serialization
3. Implement clustering algorithm in clustering_service
4. Build business_service with sample data and local storage
5. Create reusable widgets (cards, charts, containers)
6. Build home screen with dashboard overview
7. Implement business list screen with cluster filtering
8. Create add/edit business form
9. Build insights screen with visualizations
10. Update theme with modern colors
11. Run compile_project to verify implementation
