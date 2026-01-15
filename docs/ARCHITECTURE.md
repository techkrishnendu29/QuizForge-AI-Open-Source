# Architecture

QuizForge AI follows MVVM + Clean Architecture principles to keep modules maintainable and contributor-friendly.

## Layers
- Presentation: UI Screens + ViewModels
- Domain: Use Cases + core models
- Data: Repositories + local database + JSON loaders
- Generator: NLP/AI pipeline for question selection/generation

## Why this matters
- Easier onboarding for contributors
- Clear separation of responsibilities
- Safe refactoring and testing
