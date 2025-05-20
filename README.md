# rtm_visits-tracker
A Flutter-based Route-to-Market (RTM) Visits Tracker app designed for sales representatives to add, view, and track customer visits , along with task status management and visit statistics . Built with Supabase REST API integration , it supports adding visits, filtering by task status and viewing key performance stats.
# RTM Visits Tracker

A Flutter-based Route-to-Market Sales Force Automation app for tracking sales rep visits.

## Features

- Add new visits
- View list of customer visits
- Track activities completed during the visit
- View task statistics (Completed / Pending / Incomplete)
- Search/filter visits
- Offline support using Hive
- CI/CD via GitHub Actions

Key Architectural Choices

Provider for state management
Hive for offline storage
REST API via Supabase PostgREST
Modular structure for scalability
Offline Support
Visits can be saved locally using Hive and synced later when online.
Add new visits with custom customer names
View and manage their customer visit history
 Track activities performed during each visit
 View task statistics (Completed, Pending, Incomplete)
 Search or filter visits
 Navigate between multiple screens
This project integrates with a Supabase backend using PostgREST API for data persistence and retrieval.

 Screenshots of the Application
 
Key Architectural Choices
1. Architecture Pattern : MVVM-inspired
Why? It provides clear separation of concerns:
View Layer : UI widgets (views/, widgets/)
ViewModel Layer : Business logic and state management (viewmodels/)
Data Layer : REST API calls and models (core/, models/)
2. State Management : Provider
Why? Lightweight and built-in — perfect for small to medium-sized apps.
Easy to scale and test.
3. API Integration : Supabase + PostgREST
Why? Provides a clean REST interface over PostgreSQL.
Easy to use with Dart’s http package.
4. UI Design
Modularized with reusable components like VisitCard, DropdownButtonFormField, etc.
Responsive layout using ListView, Form, and BottomNavigationBar.
5. Scalability
Modular structure allows easy extension:
Add search/filter features
Plug in offline support later
Integrate with Firebase or Hive

 Set Up Instructions
1. Clone the repo
bash

git clone https://github.com/Happyoyoti/rtm-visits-tracker.git 
cd rtm-visits-tracker

2. Install dependencies
flutter pub get

3. Run the app
flutter run

4. Build APK 
flutter build apk


Notes on Optional Features

Offline Support 
Sync data when online via background tasks using hive.

Unit Tests
Using flutter_test and mockito for mocking API responses.

CI/CD (Planned)
GitHub Actions workflow for running tests and builds will be added soon.

Assumptions, Trade-offs, and Limitations
 Assumptions
Supabase backend is already set up and accessible.
Customer and activity data is preloaded in Supabase.
Internet connection is available when creating/updating visits.
 Trade-offs
Used Provider instead of more complex solutions like Bloc or Riverpod for simplicity.
No real-time updates — uses manual refresh only.
Simple filtering without advanced search options.
 Limitations
Cannot export data or generate reports.
Limited validation on form fields (can be improved).
No multi-language or dark mode support yet.
