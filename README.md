<div align="center">

<h1>🌾 Siri-Dhanya Hub</h1>

<p><strong>Millet Value Chain — Connecting Farmers & Consumers of Karnataka</strong></p>

<p><em>Siri-Dhanya Hub is a modern Android application built with Kotlin and XML that bridges the gap between millet farmers and consumers through live simulated mandi prices, Kannada recipes, health benefits, and direct FPO connect.</em></p>

<br/>

<img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" />
<img src="https://img.shields.io/badge/Language-Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white" />
<img src="https://img.shields.io/badge/UI-XML%20Layouts-4285F4?style=for-the-badge&logo=android&logoColor=white" />
<img src="https://img.shields.io/badge/Data-Local%20JSON-FF6F00?style=for-the-badge" />
<img src="https://img.shields.io/badge/Architecture-Fragment%20Based-00C853?style=for-the-badge" />
<img src="https://img.shields.io/badge/Status-Active-00C853?style=for-the-badge" />
<img src="https://img.shields.io/badge/Min%20SDK-24-blue?style=for-the-badge" />

<br/><br/>

<a href="https://drive.google.com/file/d/1ngS9DploCrhJC1xMyBFFJp4_D4-Jdt6U/view?usp=sharing">
  <img src="https://img.shields.io/badge/⬇️%20Download%20APK-v1.0.0-brightgreen?style=for-the-badge&logo=android&logoColor=white" />
</a>

</div>

---

## 📋 Table of Contents

- [Download](#-download)
- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Dependencies](#-dependencies)
- [Installation & Setup](#️-installation--setup)
- [Screenshots](#-screenshots)
- [Future Enhancements](#-future-enhancements)
- [License](#-license)
- [Author](#-author)

---

## ⬇️ Download

| Release | Link | Notes |
|---|---|---|
| v1.0.0 — Latest | [**Download APK**](https://drive.google.com/file/d/1ngS9DploCrhJC1xMyBFFJp4_D4-Jdt6U/view?usp=sharing) | Requires Android 7.0 (API 24)+ |

> **Installation note:** Since this APK is distributed outside the Play Store, you need to allow installation from unknown sources.
> Go to **Settings → Apps → Special app access → Install unknown apps** and enable it for your browser or file manager.

---

## 📱 Overview

**Siri-Dhanya Hub** (meaning *"Millet Value Chain"* in Kannada) is a millet awareness and market information app that empowers:

- **Farmers** — to know live simulated mandi prices across all 31 Karnataka districts and 36 India states/UTs for all 7 Navadhanya millets
- **Consumers** — to discover traditional Kannada millet recipes, health benefits, and connect directly with local Farmer Producer Organizations (FPOs)

The app provides a unified offline-first platform with district-wise and state-wise millet price tables, recipe search, health benefit cards, and direct FPO connect — all powered by local JSON files in the Assets folder.

---

## ✨ Features

### 🌾 Mandi Watch
- Live simulated millet prices for all 31 Karnataka districts
- India Overview with all 36 states and Union Territories
- All 7 Navadhanya millets in table format per district/state
- UP/DOWN trend indicators comparing today vs yesterday price
- 7-Day High and Low price for every millet
- TabLayout switching between Karnataka Districts and India Overview
- SearchView to filter by district or state name

### 🍲 Recipe Lab
- 8 traditional Kannada millet recipes
- SearchView filtering by millet type or recipe name
- Detailed recipe page with ingredients, method, tips, and health benefits
- Google Search fallback when recipe is not found in the list
- Smooth card-based UI with millet type and cooking time

### 💚 Health Benefits
- Detailed health facts for 5 major millets
- Benefits for diabetics, calcium content, iron, fiber
- Climate action facts — millets need 70% less water than paddy
- Color-coded cards for each millet

### 🛒 Direct Buy
- 6 local Farmer Producer Organizations (FPOs) across Karnataka
- FPO name, location, millets handled, and contact number
- Connects consumers directly with farmers — removes middlemen

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Kotlin |
| UI Toolkit | XML Layouts + Material Design |
| Navigation | BottomNavigationView + Fragment Manager |
| Architecture | Fragment-Based with Adapter Pattern |
| Data Storage | Local JSON files in Assets folder |
| JSON Parsing | org.json (JSONArray, JSONObject) |
| Image Loading | Glide 4.16.0 |
| Chart Library | MPAndroidChart v3.1.0 |
| List Display | RecyclerView + CardView |
| Search | SearchView with real-time filtering |
| Build System | Gradle (Kotlin DSL) |
| IDE | Android Studio |

---

## 🏗️ Architecture

Siri-Dhanya Hub follows a **Fragment-Based Architecture** with the **Adapter Pattern** for clean data display separation.

UI Layer (Fragments + Activities)
│
▼
Adapter Layer (RecyclerView Adapters)
│
▼
Data Model Layer (Kotlin Data Classes)
│
▼
Data Source Layer (Local JSON in Assets)

**Data flow:**
Fragments read JSON from Assets folder → Parse into Kotlin data classes → Pass to Adapters → Adapters bind data to RecyclerView rows → User sees price tables, recipe cards, and health facts.

---

## 📂 Project Structure
SiriDhanyaHub/
│
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── java/com/siridhanya/hub/
│   │       │   │
│   │       │   ├── MainActivity.kt
│   │       │   │     # Hosts all 4 fragments
│   │       │   │     # BottomNavigationView setup
│   │       │   │
│   │       │   ├── MandiFragment.kt
│   │       │   │     # Mandi Watch screen
│   │       │   │     # Reads district_prices.json
│   │       │   │     # Reads india_states.json
│   │       │   │     # TabLayout switching
│   │       │   │
│   │       │   ├── RecipesFragment.kt
│   │       │   │     # Recipe Lab screen
│   │       │   │     # SearchView filtering
│   │       │   │     # Google Search fallback
│   │       │   │
│   │       │   ├── HealthFragment.kt
│   │       │   │     # Health Benefits screen
│   │       │   │     # Dynamic card generation
│   │       │   │
│   │       │   ├── BuyFragment.kt
│   │       │   │     # Direct Buy screen
│   │       │   │     # FPO contact cards
│   │       │   │
│   │       │   ├── RecipeDetailActivity.kt
│   │       │   │     # Full recipe detail page
│   │       │   │     # Google Search integration
│   │       │   │
│   │       │   ├── DistrictAdapter.kt
│   │       │   │     # Karnataka district price table
│   │       │   │
│   │       │   ├── IndiaAdapter.kt
│   │       │   │     # India state price table
│   │       │   │
│   │       │   ├── RecipeAdapter.kt
│   │       │   │     # Recipe card list
│   │       │   │     # Click → RecipeDetailActivity
│   │       │   │
│   │       │   ├── FpoAdapter.kt
│   │       │   │     # FPO contact card list
│   │       │   │
│   │       │   ├── MandiModels.kt
│   │       │   │     # MilletPrice data class
│   │       │   │     # DistrictPrice data class
│   │       │   │     # IndiaState data class
│   │       │   │
│   │       │   ├── RecipeItem.kt
│   │       │   │     # Recipe data class
│   │       │   │
│   │       │   └── FpoItem.kt
│   │       │         # FPO contact data class
│   │       │
│   │       ├── assets/
│   │       │   ├── district_prices.json
│   │       │   │     # 31 Karnataka districts
│   │       │   │     # 7 millets each with price,
│   │       │   │     # yesterday, last7 array
│   │       │   │
│   │       │   └── india_states.json
│   │       │         # 36 states and UTs
│   │       │         # 7 millets each
│   │       │
│   │       └── res/
│   │           ├── layout/
│   │           │     ├── activity_main.xml
│   │           │     ├── activity_recipe_detail.xml
│   │           │     ├── fragment_mandi.xml
│   │           │     ├── fragment_recipes.xml
│   │           │     ├── fragment_health.xml
│   │           │     ├── fragment_buy.xml
│   │           │     ├── item_district.xml
│   │           │     ├── item_india_state.xml
│   │           │     ├── item_recipe.xml
│   │           │     └── item_fpo.xml
│   │           │
│   │           ├── menu/
│   │           │     └── bottom_nav_menu.xml
│   │           │
│   │           ├── drawable/
│   │           │     └── ic_launcher_foreground.xml
│   │           │           # Custom millet stalk logo
│   │           │
│   │           └── values/
│   │                 ├── colors.xml
│   │                 ├── strings.xml
│   │                 └── themes.xml
│   │
│   └── build.gradle.kts
│
├── gradle/
│   └── libs.versions.toml
├── build.gradle.kts
├── settings.gradle.kts
└── README.md

---

## ✅ Prerequisites

Before you begin, ensure you have the following installed:

| Tool | Minimum Version | Download |
|---|---|---|
| Android Studio | Meerkat (2024.1.1) | [Download](https://developer.android.com/studio) |
| JDK | 17 | Bundled with Android Studio |
| Android SDK | API 24 (min) / API 36 (target) | Via SDK Manager |
| Kotlin | 2.0.21 | Bundled with Android Studio |
| Gradle | 9.0.1 | Auto-downloaded via wrapper |
| Git | Latest | [Download](https://git-scm.com) |

---

## 📦 Dependencies

All versions are managed centrally in `gradle/libs.versions.toml`.

### `gradle/libs.versions.toml`
```toml
[versions]
agp = "9.0.1"
kotlin = "2.0.21"
coreKtx = "1.18.0"
junit = "4.13.2"
junitVersion = "1.3.0"
espressoCore = "3.7.0"
appcompat = "1.6.1"
material = "1.11.0"
constraintlayout = "2.1.4"
recyclerview = "1.3.2"
cardview = "1.0.0"

[libraries]
androidx-core-ktx = { group = "androidx.core", name = "core-ktx", version.ref = "coreKtx" }
androidx-appcompat = { group = "androidx.appcompat", name = "appcompat", version.ref = "appcompat" }
material = { group = "com.google.android.material", name = "material", version.ref = "material" }
androidx-constraintlayout = { group = "androidx.constraintlayout", name = "constraintlayout", version.ref = "constraintlayout" }
androidx-recyclerview = { group = "androidx.recyclerview", name = "recyclerview", version.ref = "recyclerview" }
androidx-cardview = { group = "androidx.cardview", name = "cardview", version.ref = "cardview" }
junit = { group = "junit", name = "junit", version.ref = "junit" }
androidx-junit = { group = "androidx.test.ext", name = "junit", version.ref = "junitVersion" }
androidx-espresso-core = { group = "androidx.test.espresso", name = "espresso-core", version.ref = "espressoCore" }

[plugins]
android-application = { id = "com.android.application", version.ref = "agp" }
kotlin-android = { id = "org.jetbrains.kotlin.android", version.ref = "kotlin" }
```

### `app/build.gradle.kts` — Dependencies Block
```kotlin
dependencies {
    implementation(libs.androidx.core.ktx)
    implementation(libs.androidx.appcompat)
    implementation(libs.material)
    implementation(libs.androidx.constraintlayout)
    implementation(libs.androidx.recyclerview)
    implementation(libs.androidx.cardview)

    // Glide for food image loading
    implementation("com.github.bumptech.glide:glide:4.16.0")

    // MPAndroidChart for 7-day price trend
    implementation("com.github.PhilJay:MPAndroidChart:v3.1.0")

    testImplementation(libs.junit)
    androidTestImplementation(libs.androidx.junit)
    androidTestImplementation(libs.androidx.espresso.core)
}
```

---

## ⚙️ Installation & Setup

### Step 1 — Clone the Repository
```bash
git clone https://github.com/SUMUKHASRIVATSAL-OFFICIAL/SiriDhanyaHub.git
cd SiriDhanyaHub
```

### Step 2 — Open in Android Studio
1. Launch **Android Studio**
2. Select **File → Open** and choose the `SiriDhanyaHub/` folder
3. Wait for the IDE to index the project

### Step 3 — Sync Gradle
Click **"Sync Now"** in the notification bar, or run:
```bash
./gradlew build
```

### Step 4 — Run the App
- Connect a physical Android device (API 24+) via USB with Developer Options and USB Debugging enabled
- Press **Run ▶** (Shift + F10)
- The app will install and launch on your device

> **Note:** No internet connection is required. All data is stored locally in JSON files inside the Assets folder.

---

## 📸 Screenshots

<div align="center">

<table>
  <tr>
    <td align="center"><b>Mandi Watch — Karnataka</b></td>
    <td align="center"><b>Mandi Watch — India</b></td>
    <td align="center"><b>Recipe Lab</b></td>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/ece292b8-d209-4d5b-9e0d-849c506f4ad4" width="220"/></td>
    <td><img src="https://github.com/user-attachments/assets/cb9d932f-ebb5-4566-8acd-90157e41d919" width="220"/></td>
    <td><img src="https://github.com/user-attachments/assets/168d216c-b5dc-4817-8d2e-f3101a37d1a0" width="220"/></td>
  </tr>
  <tr>
    <td align="center"><b>Health Benefits</b></td>
    <td align="center"><b>Direct Buy</b></td>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/79776f94-ff38-416d-b444-20cf661f6100" width="220"/></td>
    <td><img src="https://github.com/user-attachments/assets/8ee48a7d-75f9-4c4c-885d-99e3dadb634d" width="220"/></td>
  </tr>
</table>

</div>

---

## 📈 Future Enhancements

| Feature | Description |
|---|---|
| 🔔 Price Alert Notifications | FCM-based alerts when millet price crosses threshold |
| 🌐 Live Mandi API | Connect to Agmarknet or eNAM for real-time prices |
| 💳 Payment Gateway | In-app payment support via Razorpay for Direct Buy |
| 📍 Location-Based Mandi | Show nearest mandi based on farmer's GPS location |
| 🗣️ Kannada Language Support | Full Kannada UI for semi-literate farmers |
| 🤖 AI Recipe Suggestions | GenAI-powered recipe recommendations based on millet availability |
| 👤 Farmer Profile | Login and profile for farmers to track prices and orders |
| 📊 Price History Chart | Interactive 30-day price chart using MPAndroidChart |
| ☁️ Cloud Sync | Firebase integration for real-time price updates |
| 🎙️ Voice Assistant | Audio-based navigation for low-literacy users |

---

## 📄 License

This project is developed for educational and internship purposes under the MindMatrix VTU Internship Program. All rights reserved by the author.

---

## 👨‍💻 Author

<div align="center">

### Sumukha Srivatsa L
**BE in Computer Science Engineering**

Android Developer · Kotlin Learner · Agriculture Tech Enthusiast

MindMatrix VTU Internship Program
Project 74 — Android App Development using GenAI — Siri-Dhanya Hub (Agriculture)

[![GitHub](https://img.shields.io/badge/GitHub-SUMUKHASRIVATSAL--OFFICIAL-181717?style=for-the-badge&logo=github)](https://github.com/SUMUKHASRIVATSAL-OFFICIAL/SiriDhanyaHub)

</div>

---

<div align="center">
  <sub>If you found this project helpful, please consider giving it a ⭐ on GitHub!</sub>
  <br/>
  <sub>🌾 Promoting Karnataka's Navadhanya millets through technology</sub>
</div>


