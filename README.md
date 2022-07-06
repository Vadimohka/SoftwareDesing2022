## Table of Contents
- [General requirements](#General-requirements)
- [Tasks](#Tasks)
  - [Lab 1 - Americans are asleep. Upvote the metric system!](#1-Americans-are-asleep-Upvote-the-metric-system)
  - [Lab 2 - Nobody runs away from the military commissariat!](#2-Nobody-runs-away-from-the-military-commissariat)
  - [Lab 3 - The Numbers Mason! What do they Mean?](#3-the-numbers-mason!-what-do-they-mean?)
  - [Lab 4 - You wanna play? Let's play!](#4-you-wanna-play-lets-play)
- [Clarifications](#Clarifications)

# General requirements

## VCS
All work have to be performed inside a **git repository**. Each application can be developed in the separate branch, or in separate folder within one branch.

## Versioning
Every application should be 'equipped' with **basic versioning** implementation. Resulting application package should have proper `versionCode` and `versionName` (make sure to find out what are the differences between these values) according to SEMVER (Semantic Versioning). Version name should contain major, minor and patch version numbers. A version tracking should be performed by utilizing git tag feature. Each tag should be formatted as `MAJOR.MINOR` (e.g. 1.3), PATCH number represents a number of commits performed after latest release (latest tag) (all numbers are obtained via git shell commands).

### Further reading:
- [Android app versioning](https://developer.android.com/studio/publish/versioning)
- [Tags in git](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
- [Git and gradle integration example](https://gist.github.com/erics/1c6e333b70508be01c884b7e54d8cfbf)
- [Official start course from Google](https://developer.android.com/courses)
- [Android Jetpack](https://developer.android.com/jetpack)
- [Samples](https://developer.android.com/samples)
- [Great example](https://github.com/android/nowinandroid)

## App signing
Resulting **release** APK should be signed with a personal certificate automatically during build. You have to understand why this action is important.

### Further reading:
- [App signing](https://developer.android.com/studio/publish/app-signing)

## Languages
Kotlin, Dart (Flutter), React Native, Swift (for iOS).
Xamarin and Java allowed in agreement with the teacher

# Tasks

## 1. 'Americans are asleep. Upvote the metric system!'
A 'Unit/Currency Converter' application.

1. Minumum 3 different unit categories (distance, weight, currency, etc)
2. At least 3 different units in each category.
3. Calculator-like num pad and two fields for original and converted values. The user should not be able to change data in these fields with default system keyboard.
4. A keyboard and data should be in separate android fragments.
   - portrait orientation: fragments are placed in a row (keyboard below data fragment)
   - landscape orientation: fragments have to be aligned in line.
5. Create a 'premium' build flavour.
   - There should be a button, that will switch initial and converted values (and units) and vice-versa.
   - A button to copy current value to the clipboard near each data field.
   - Use source sets to define different layouts and files with code for each flavour.

**Topics to cover:** gradle, build variants, product flavors, activities, fragments, activity lifecycle, views, controls, basic app architecture, product flavors.

### Further reading:
- [Android Activities](https://developer.android.com/guide/components/activities/intro-activities)
- [Activity Lifecycle](https://developer.android.com/guide/components/activities/activity-lifecycle) / [Extended diagram](https://github.com/xxv/android-lifecycle)
- [Activity Fragments](https://developer.android.com/guide/components/fragments)
- [Layouts in Android](https://developer.android.com/guide/topics/ui/declaring-layout)
- [Android Architecture components](https://developer.android.com/topic/libraries/architecture) - a good way to implement MVVM and structure your app
   - [LiveData](https://developer.android.com/topic/libraries/architecture/livedata)
   - [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel)
- [Build variants](https://developer.android.com/studio/build/build-variants)


## 2. 'Nobody runs away from the military commissariat!'
A 'Tabata timer' application. ([Reference](https://play.google.com/store/apps/details?id=com.evgeniysharafan.tabatatimer&hl=ru))

1. A user can create different timer sequences and switch between them (use GSON or SQLite for data storage).
2. Home page - a list of sequences
   - CRUD for them
3. Sequence properties:
   - title
   - colour
4. Timer page:
   - remaining time of the current phase
   - list of upcoming phases
   - controls to pause, go back and forth through the sequence or to leave this page and cancel the timer
5. Edit page:
   - tweak duration of each phase (workout, rest, warm-up, cooldown)
   - change number of phase repetitions and rest periods between them
   - define sequence properties
6. While running, each phase switch should trigger a sound to warn user.
7. The timer should not stop when user leaves the app (see Services).
8. Settings page (implemented with AndroidX Preference library):
   - day / night theme
   - change app font size (without app reload)
   - a button to clear all stored data
   - switch app locale (a choice between two languages at least).
9. Application should have a splash screen with app name or artwork to entertain the user while the app is being loaded.

**Topics to cover:** data storage, app architecture, styling, services, preferences.

### Further reading:
- [Permissions](https://developer.android.com/guide/topics/permissions/overview)
- [Room Database](https://developer.android.com/training/data-storage/room) / [Data storage](https://developer.android.com/training/data-storage/app-specific)
- [Services](https://developer.android.com/guide/components/services)
- [Preferences](https://developer.android.com/guide/topics/ui/settings)
- [Style and theme](https://developer.android.com/guide/topics/ui/look-and-feel/themes)


## 3. 'The Numbers Mason! What do they Mean?'

1. Create 'Calculator' app.
2. Application should have two modes: basic and scientific (see, well, any calculator for reference).
3. Modes can be toggled via interface button.
4. Each set of functions (numbers + basic functions and scientific functions) should be in separate fragments.
5. For landscape device orientation app should always be in scientific mode.
6. Create a 'demo' build flavor with only basic functions available for both screen orientations. User should be able to have both 'demo' and 'full' versions on device at the same time.


## 4. 'You wanna play? Let's play!'
Online  'Battleship' or 'Chess' game.

1. Two players should be able to participate in the game from different devices.
2. Firebase Firestore / RealtimeDB or similar service as a back-end.
3. Authentication using any auth provider (Google, social network, etc) or plain email-password pair.
4. User 1 creates a game and shares generated game ID with opponent.
5. Opponent (user 2) joins the game via given ID.
6. User 1 device acts as a server and is responsible for game state updates.
7. User 2 device subscribes to state changes in DB and updates interface.
8. User statistics page with previous games
9. User profile page:
    - nickname change
    - avatar (user can switch between these two options in profile)
      - remote storage using Firebase File storage
      - [Gravatar](https://ru.gravatar.com/)

**Topics to cover:** network, async operations, advanced UI practices.

### Further reading:
- [Firbase for Android](https://firebase.google.com/docs/android/setup)
- [Firestore](https://firebase.google.com/docs/firestore)
- [Fresco](https://frescolib.org/docs/index.html) / [Picasso](https://square.github.io/picasso/) - libraries to work with images
- [Volley overview](https://developer.android.com/training/volley) / [OkHTTP](https://square.github.io/okhttp/) - libraries for network operations

# Clarifications
If you need a clarification regarding tasks or required app functions, use Github Issues to ask a question. If you have questions regarding implementation, a face-to-face conversation is the best way to discuss them. But you can also reach me via Telegram, if you want to. Contact information will be given to you during first gatherings.
