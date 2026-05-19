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

<a href="YOUR_APK_GOOGLE_DRIVE_LINK_HERE">
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
| v1.0.0 — Latest | [**Download APK**](YOUR_APK_GOOGLE_DRIVE_LINK_HERE) | Requires Android 7.0 (API 24)+ |

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
