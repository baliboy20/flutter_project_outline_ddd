# Flutter DDD Project Structure

```
lib/
├── main.dart
├── app.dart
│
├── core/                           # Shared core functionality
│   ├── constants/
│   │   ├── app_constants.dart
│   │   ├── api_constants.dart
│   │   └── storage_constants.dart
│   │
│   ├── error/
│   │   ├── exceptions.dart
│   │   ├── failures.dart
│   │   └── error_handler.dart
│   │
│   ├── network/
│   │   ├── dio_client.dart
│   │   ├── api_client.dart
│   │   ├── interceptors/
│   │   │   ├── auth_interceptor.dart
│   │   │   ├── logging_interceptor.dart
│   │   │   └── error_interceptor.dart
│   │   └── network_info.dart
│   │
│   ├── storage/
│   │   ├── hive_service.dart
│   │   ├── storage_service.dart
│   │   └── adapters/
│   │       └── user_adapter.dart
│   │
│   ├── utils/
│   │   ├── date_utils.dart
│   │   ├── validation_utils.dart
│   │   ├── extensions/
│   │   │   ├── string_extensions.dart
│   │   │   └── context_extensions.dart
│   │   └── helpers/
│   │       └── navigation_helper.dart
│   │
│   ├── theme/
│   │   ├── app_theme.dart
│   │   ├── app_colors.dart
│   │   └── app_text_styles.dart
│   │
│   └── injection/
│       └── dependency_injection.dart
│
├── shared/                         # Shared across features
│   ├── domain/
│   │   ├── entities/
│   │   │   └── base_entity.dart
│   │   ├── repositories/
│   │   │   └── base_repository.dart
│   │   └── usecases/
│   │       └── usecase.dart
│   │
│   ├── data/
│   │   ├── models/
│   │   │   └── base_model.dart
│   │   └── datasources/
│   │       ├── local_datasource.dart
│   │       └── remote_datasource.dart
│   │
│   └── presentation/
│       ├── widgets/
│       │   ├── custom_button.dart
│       │   ├── custom_text_field.dart
│       │   ├── loading_indicator.dart
│       │   └── error_widget.dart
│       ├── bloc/
│       │   └── base_bloc.dart
│       └── pages/
│           ├── splash_page.dart
│           └── not_found_page.dart
│
├── features/                       # Feature-based organization
│   ├── authentication/
│   │   ├── domain/
│   │   │   ├── entities/
│   │   │   │   ├── user.dart
│   │   │   │   └── auth_token.dart
│   │   │   ├── repositories/
│   │   │   │   └── auth_repository.dart
│   │   │   └── usecases/
│   │   │       ├── login_usecase.dart
│   │   │       ├── logout_usecase.dart
│   │   │       ├── register_usecase.dart
│   │   │       ├── refresh_token_usecase.dart
│   │   │       └── get_current_user_usecase.dart
│   │   │
│   │   ├── data/
│   │   │   ├── models/
│   │   │   │   ├── user_model.dart
│   │   │   │   ├── auth_token_model.dart
│   │   │   │   ├── login_request_model.dart
│   │   │   │   └── register_request_model.dart
│   │   │   ├── repositories/
│   │   │   │   └── auth_repository_impl.dart
│   │   │   └── datasources/
│   │   │       ├── auth_local_datasource.dart
│   │   │       └── auth_remote_datasource.dart
│   │   │
│   │   └── presentation/
│   │       ├── bloc/
│   │       │   ├── auth_bloc.dart
│   │       │   ├── auth_event.dart
│   │       │   ├── auth_state.dart
│   │       │   ├── login/
│   │       │   │   ├── login_bloc.dart
│   │       │   │   ├── login_event.dart
│   │       │   │   └── login_state.dart
│   │       │   └── register/
│   │       │       ├── register_bloc.dart
│   │       │       ├── register_event.dart
│   │       │       └── register_state.dart
│   │       ├── pages/
│   │       │   ├── login_page.dart
│   │       │   ├── register_page.dart
│   │       │   └── forgot_password_page.dart
│   │       └── widgets/
│   │           ├── login_form.dart
│   │           ├── register_form.dart
│   │           └── auth_button.dart
│   │
│   ├── dashboard/
│   │   ├── domain/
│   │   │   ├── entities/
│   │   │   │   └── dashboard_data.dart
│   │   │   ├── repositories/
│   │   │   │   └── dashboard_repository.dart
│   │   │   └── usecases/
│   │   │       └── get_dashboard_data_usecase.dart
│   │   │
│   │   ├── data/
│   │   │   ├── models/
│   │   │   │   └── dashboard_data_model.dart
│   │   │   ├── repositories/
│   │   │   │   └── dashboard_repository_impl.dart
│   │   │   └── datasources/
│   │   │       ├── dashboard_local_datasource.dart
│   │   │       └── dashboard_remote_datasource.dart
│   │   │
│   │   └── presentation/
│   │       ├── bloc/
│   │       │   ├── dashboard_bloc.dart
│   │       │   ├── dashboard_event.dart
│   │       │   └── dashboard_state.dart
│   │       ├── pages/
│   │       │   └── dashboard_page.dart
│   │       └── widgets/
│   │           ├── dashboard_card.dart
│   │           └── stats_widget.dart
│   │
│   ├── profile/
│   │   ├── domain/
│   │   │   ├── entities/
│   │   │   │   └── user_profile.dart
│   │   │   ├── repositories/
│   │   │   │   └── profile_repository.dart
│   │   │   └── usecases/
│   │   │       ├── get_profile_usecase.dart
│   │   │       └── update_profile_usecase.dart
│   │   │
│   │   ├── data/
│   │   │   ├── models/
│   │   │   │   └── user_profile_model.dart
│   │   │   ├── repositories/
│   │   │   │   └── profile_repository_impl.dart
│   │   │   └── datasources/
│   │   │       ├── profile_local_datasource.dart
│   │   │       └── profile_remote_datasource.dart
│   │   │
│   │   └── presentation/
│   │       ├── bloc/
│   │       │   ├── profile_bloc.dart
│   │       │   ├── profile_event.dart
│   │       │   └── profile_state.dart
│   │       ├── pages/
│   │       │   ├── profile_page.dart
│   │       │   └── edit_profile_page.dart
│   │       └── widgets/
│   │           ├── profile_avatar.dart
│   │           └── profile_form.dart
│   │
│   └── [other_features]/           # Add more features as needed
│       └── ... (same structure)
│
├── config/                         # Configuration files
│   ├── routes/
│   │   ├── app_router.dart
│   │   └── route_names.dart
│   └── environment/
│       ├── environment.dart
│       ├── dev_config.dart
│       └── prod_config.dart
│
└── generated/                      # Generated files
    ├── l10n/
    └── hive/
```

## Key Structure Principles

### 1. **Core Layer**
- Contains shared utilities, services, and infrastructure
- Network setup with Dio
- Hive storage configuration
- Dependency injection setup

### 2. **Shared Layer**
- Common widgets, base classes, and utilities used across features
- Ensures consistency and reduces code duplication

### 3. **Features Layer**
- Each feature follows clean architecture (domain, data, presentation)
- **Domain**: Business logic, entities, use cases, repository contracts
- **Data**: Implementation details, models, data sources
- **Presentation**: UI components, BLoC, pages, widgets

### 4. **Clean Architecture Flow**
```
Presentation → Domain ← Data
     ↓           ↓        ↓
   BLoC    →  UseCase  ← Repository
     ↓           ↓        ↓
   Widget      Entity   DataSource
```

### 5. **Authentication Integration**
- Centralized auth management
- Token storage in Hive
- HTTP interceptors for automatic token injection
- Auth state management with BLoC

### 6. **Configuration**
- Routing setup
- Environment-based configuration
- Generated files for localization and Hive adapters