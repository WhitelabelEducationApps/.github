# Whitelabel Education Apps

Building reusable, multiplatform educational applications powered by shared whitelabel modules.

## Apps

### [MuseumKMP](https://github.com/WhitelabelEducationApps/MuseumKMP)
UNESCO World Heritage Sites - 1,150+ sites across 10 languages with interactive maps, search, favorites, and wallpaper integration. Groups items by country.

### [HerbalRedo](https://github.com/WhitelabelEducationApps/HerbalRedo)
Medicinal plants encyclopedia - 600+ plants across 12 languages with category grouping, location-based filtering, and botanical knowledge.

Both apps are thin shells: a custom Application class, a one-line Activity, app-specific string resources, a pre-built SQLite database, and a Koin module that wires AppConfig + an optional custom ItemGrouper. All shared logic lives in the whitelabel modules below.

## Shared Libraries

### [whitelabel-core](https://github.com/WhitelabelEducationApps/whitelabel-core)
Domain abstractions and base ViewModels shared across all apps.

- DisplayableItem interface, ItemRepository<T>, Result type
- HomeViewModel<T> with search, language switching, reactive filtering
- ItemDetailViewModel, LanguageSelectionViewModel
- AppConfig feature flags (enableMap, enableCategories, enableLocationFilter)
- ItemGrouper<T> strategy for custom item grouping per app

### [whitelabel-platform](https://github.com/WhitelabelEducationApps/whitelabel-platform)
Concrete data layer, full UI, and platform services.

- SQLDelight schema (CatalogItem, Author) and ItemRepository implementation
- Complete Compose Multiplatform UI: home grid, detail screen, language picker, map, navigation
- WhitelabelActivity base class, AppNavigation, Material Design 3 theme
- Platform services: wallpaper, image preloading, color extraction
- Koin DI modules (commonModule, viewModelModule, platformModule)
- Runtime string resource lookup via getStringResource()

## How It Works

Each app includes both whitelabel modules as git submodules wired through Gradle composite builds (includeBuild()). The app's Koin module loads last, overriding bindings from the whitelabel modules.

## Tech Stack

- **Language:** Kotlin Multiplatform (KMP) 2.x
- **UI:** Jetpack Compose Multiplatform
- **Database:** SQLDelight (via whitelabel-core schema)
- **Async:** Coroutines and Flow
- **DI:** Koin 4.0
- **Design:** Material Design 3

## Getting Started

Clone any app with submodules:

git clone --recursive https://github.com/WhitelabelEducationApps/MuseumKMP.git

Build and run:

./gradlew :androidApp:installDebug

## Vision

A suite of educational applications that are:
- **Reusable** - shared whitelabel modules eliminate code duplication
- **Multiplatform** - iOS and Android from a single codebase
- **Scalable** - new apps need only content, config, and a grouper
- **Accessible** - multilingual and inclusive design
- **Offline-first** - work without constant internet

## Contributing

All projects are open-source. Check individual repos for contribution guidelines.

## License

Projects are open-source. See individual repositories for license details.

---

**Organization Lead:** [@rsavutiu](https://github.com/rsavutiu)
**Last Updated:** May 2026
