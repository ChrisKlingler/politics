# Politics

A starter Flutter project integrated with Supabase for building grassroots civic engagement apps.

🎯 **Features include**:
- Email/magic-link authentication (Supabase Auth)
- PostgreSQL schema and RLS-ready backend
- Image uploads using Supabase Storage
- Clean architecture with feature-based separation
- Dark mode support, local caching, and DI setup

This repo is forked from [miljepetrovic/flutter_supabase_starter_template] and adapted as a foundation for LibbedUp-style political and community organizing tools.

## 🚀 Getting Started

1. Clone this repo
2. Add your Supabase credentials to `.env`
3. Run `flutter pub get`
4. Launch with `flutter run`

## 🤝 Contributing

Open source — built for collaboration!
See CONTRIBUTING.md for guidance on how to help shape this project.


## Available features

* Clean architecture with the feature-first-project structure where features are separated into 3 modules: data, domain, and presentation.
* State management with BLoC/Cubit
* Dependency injection using GetIt and Injectable
* Navigation with GoRouter
* Dark mode
* Hive as a local database
* Supabase integration
* Authentication flow using login with a magic link
* Change email address
* Settings page with Privacy Policy and Terms of Service links
* Flutter Native Splash Screen
* Flutter Launcher Icons
* Google Fonts

## Setup 

### Supabase 

1. **Create Supabase Project**: Visit [Supabase](https://supabase.com/) and create a new project.
2. **Enable Email Provider**: Navigate to the Authentication page in the Supabase dashboard. In the Configuration tab, enable the Email Provider. In our simple example, we disabled Secure Email Change. This is not our recommendation and we consider enabling it in production would be helpful.
3. **Configure URL Callbacks**: In the URL Configuration section, add the Site URL and Redirect URLs for login and change email address callbacks. Replace **testproject** with the name of your Supabase project.


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Site URL:** 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; io.supabase.testproject


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Redirect URLs:**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; io.supabase.testproject://login-callback/
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  io.supabase.testproject://change-email/


### Flutter

1. Run **flutter pub get**
2. Add Supabase Project URL and Public Anon Key:
    * In your main.dart file, locate the **_initializeSupabase()** method.
    * Replace **PROJECT_URL** and **PUBLIC_ANON_KEY** with your Supabase project URL and public anon key respectively. You can find these in the API settings tab inside the Project Settings section on Supabase.
3. Setup Deeplinking URLs:
    * Edit the **ios/Runner/Info.plist** file: Update **CFBundleURLSchemes** to match your Site URL.
    * Edit the **android/app/src/main/AndroidManifest.xml** file: Update intent-filter to match the scheme and host of your Site URL and Redirect URLs.
    * Open **/lib/core/constants/urls.dart** and update **_baseSupabaseUrl** to match your Site URL.
