<p align="center"><img src="docs/icon.png" width="96" alt="App icon"/></p>

# 💰 Quản Lý Chi Tiêu — Personal Finance for Android

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Android](https://img.shields.io/badge/Android-API_21+-3DDC84?style=flat-square&logo=android&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)

An Android app for tracking personal income and spending. Its standout feature: it **listens for bank SMS notifications and logs the transaction for you**, so you don't have to type every payment in by hand.

<!-- Add 2–3 screenshots here, e.g.:
<p align="center">
  <img src="docs/home.png" width="230"/> <img src="docs/report.png" width="230"/> <img src="docs/add.png" width="230"/>
</p>
-->

## ✨ Features

- **Automatic logging from bank SMS** — a background `SmsListenerService` detects messages from 16 Vietnamese banks (Vietcombank, VietinBank, BIDV, Techcombank, MB Bank, ACB, TPBank, VPBank, …) and extracts the +/− amount
- **Transactions** — add, edit and view details; group by category with icons (food, coffee, bills, travel, …)
- **Reports** — pie chart of spending by category over a custom date range
- **Wallet setup** — enter starting balance on first launch
- **Notifications** — in-app list of detected transactions
- **Accounts** — register, log in, change password
- **Offline-first** — all data stored locally in SQLite

## 🧱 Tech stack

| | |
|---|---|
| Language | Java |
| Platform | Android (minSdk 21, targetSdk 29), AndroidX |
| Storage | SQLite (`SQLiteUtil`), SharedPreferences |
| UI | Material Components, CircleImageView |
| Charts | [MPAndroidChart](https://github.com/PhilJay/MPAndroidChart) |

## 📂 Project structure

```
app/src/main/java/.../quanlychitieu/
├── activity/   # Login, Register, Main, Add/Edit/Detail transaction, date range picker
├── fragment/   # Transactions, Report, Notifications, More
├── adapter/    # ListView adapters
├── model/      # Transaction, TransactionGroup, WalletType, Notification…
├── service/    # SmsListenerService, MessageListener
└── util/       # SMS parsing, SQLite, date/number helpers
```

## ▶️ Run locally

1. Clone the repo and open it in **Android Studio**.
2. Let Gradle sync, then run on a device or emulator (Android 5.0+).
3. Grant **SMS permission** when asked — needed for automatic transaction logging.

Requires JDK 11 (Android Gradle Plugin 7.2, Gradle 7.3.3).

## 👥 Team

- Trần Hoàng Anh
- Võ Bách Thành Nhân
- Nguyễn Đức Đạo
- Nguyễn Ngọc Minh
