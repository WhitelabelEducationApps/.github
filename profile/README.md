# Whitelabel Education Apps

Building reusable, multiplatform educational applications for cultural heritage sites.

## Projects

### [MuseumKMP](https://github.com/WhitelabelEducationApps/MuseumKMP)
A Kotlin Multiplatform application showcasing UNESCO World Heritage Sites with rich multilingual content, maps, search, and personalization features.

**Tech Stack:** Kotlin Multiplatform • Compose Multiplatform • SQLDelight • Clean Architecture

**Features:**
- 1,200+ UNESCO World Heritage Sites
- 10+ languages (English, French, Spanish, German, Italian, Portuguese, Russian, Arabic, Chinese, Japanese)
- Interactive maps with site clustering
- Advanced search and filtering
- Favorites & personalization
- Wallpaper integration (Android)
- Offline-first with local SQLite database

## Shared Libraries

### [whitelabel-platform](https://github.com/WhitelabelEducationApps/whitelabel-platform)
Reusable KMP library with core components, utilities, and abstractions for building heritage site applications.

**Includes:**
- Localization & language management
- Generic UI components & Material Design 3 theming
- Platform services (wallpaper, image preloading, color extraction)
- Utilities (logging, strings, colors, context helpers)

### [whitelabel-core](https://github.com/WhitelabelEducationApps/whitelabel-core)
Core domain logic, data layer abstractions, and business use cases shared across applications.

**Includes:**
- Domain models & repositories
- Use cases & business logic
- SQLDelight database schemas
- Data source abstractions

## Architecture

All projects follow **Clean Architecture** with clear separation of concerns:

```
Presentation Layer (UI, ViewModels, Screens)
    ↓
Domain Layer (Use Cases, Repositories, Models)
    ↓
Data Layer (Data Sources, Database, Network)
```

## Tech Stack

- **Language:** Kotlin Multiplatform (KMP)
- **UI:** Jetpack Compose Multiplatform
- **Database:** SQLDelight with Room 3 (KSP, SQLiteDriver)
- **Async:** Coroutines & Flow
- **DI:** Manual DI with AppModule pattern
- **Design:** Material Design 3

## Getting Started

### Clone with Submodules
```bash
git clone --recursive https://github.com/WhitelabelEducationApps/MuseumKMP.git
cd MuseumKMP
```

### Build & Run
```bash
# Sync dependencies
./gradlew build

# Run Android app
./gradlew :androidApp:installDebug
```

## Vision

Create a suite of educational applications for cultural heritage sites that are:
- **Reusable** — Shared libraries minimize code duplication
- **Multiplatform** — iOS & Android from single codebase
- **Scalable** — Easy to add new educational applications
- **Accessible** — Multilingual and inclusive design
- **Offline-first** — Work without constant internet

## Contributing

All projects are open-source. Check individual repos for contribution guidelines.

## License

Projects are open-source. See individual repositories for license details.

---

**Organization Lead:** [@rsavutiu](https://github.com/rsavutiu)  
**Last Updated:** April 2026
