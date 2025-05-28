# 📱 BirJob iOS App

A modern, native iOS application for job search in Azerbaijan, connecting job seekers with opportunities from 50+ sources. Built with SwiftUI and integrated with the comprehensive BirJob backend API.

![iOS](https://img.shields.io/badge/iOS-15.0+-blue.svg)
![Swift](https://img.shields.io/badge/Swift-5.8-orange.svg)
![SwiftUI](https://img.shields.io/badge/SwiftUI-4.0-blue.svg)
![Xcode](https://img.shields.io/badge/Xcode-15.0+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Screenshots](#screenshots)
- [Architecture](#architecture)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [API Integration](#api-integration)
- [Push Notifications](#push-notifications)
- [Development](#development)
- [Testing](#testing)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)

## 🌟 Overview

BirJob iOS app is the premier job search application for Azerbaijan, providing users with access to thousands of job opportunities from leading companies and job boards. The app features intelligent job recommendations, real-time notifications, and a seamless user experience designed specifically for mobile job seekers.

### Key Highlights
- **Native iOS Experience**: Built with SwiftUI for optimal performance and user experience
- **Comprehensive Job Search**: Access to 50+ job sources with advanced filtering
- **Smart Notifications**: Personalized job alerts based on user preferences
- **Offline Support**: Browse saved jobs without internet connection
- **Real-time Updates**: Live job notifications and instant search results
- **Analytics Integration**: Track user behavior for improved recommendations

## ✨ Features

### 🔍 Advanced Job Search
- **Smart Search**: Intelligent search with autocomplete and suggestions
- **Advanced Filters**: Filter by company, source, date, and custom criteria
- **Saved Searches**: Save frequent searches for quick access
- **Search History**: Access previously searched terms
- **Trending Jobs**: Discover popular and trending job opportunities

### 📊 Personalized Experience
- **Custom Keywords**: Set up personalized job alert keywords
- **Source Preferences**: Choose preferred job sources and companies
- **Job Recommendations**: AI-powered job recommendations based on profile
- **Saved Jobs**: Bookmark interesting positions for later review
- **Application Tracking**: Track job applications and their status

### 🔔 Smart Notifications
- **Real-time Alerts**: Instant notifications for matching job opportunities
- **Customizable Frequency**: Control notification frequency and timing
- **Rich Notifications**: Detailed job information in notification previews
- **Silent Hours**: Configure quiet hours for notifications
- **Notification History**: Review all received job alerts

### 🎨 Modern User Interface
- **SwiftUI Design**: Native iOS design following Human Interface Guidelines
- **Dark Mode Support**: Automatic light/dark mode switching
- **Accessibility**: Full VoiceOver and accessibility feature support
- **Haptic Feedback**: Tactile feedback for enhanced user interaction
- **Smooth Animations**: Fluid transitions and micro-interactions

### 📱 Mobile-Optimized Features
- **Offline Mode**: Access saved jobs without internet connection
- **Quick Actions**: 3D Touch shortcuts for common actions
- **Widget Support**: Home screen widgets for job updates
- **Handoff**: Continue job searches across devices
- **Spotlight Search**: Search jobs directly from iOS Spotlight

### 🔐 Privacy & Security
- **Data Privacy**: Local data encryption and secure API communication
- **Biometric Authentication**: Face ID / Touch ID for app access
- **Privacy Controls**: Granular privacy settings and data management
- **Secure Storage**: Keychain integration for sensitive data
- **GDPR Compliance**: Full compliance with data protection regulations

## 📸 Screenshots

### Home & Search
| Home Screen | Job Search | Filter Options |
|-------------|-----------|----------------|
| ![Home](screenshots/home.png) | ![Search](screenshots/search.png) | ![Filters](screenshots/filters.png) |

### Job Details & Profile
| Job Details | User Profile | Notifications |
|-------------|--------------|---------------|
| ![Details](screenshots/details.png) | ![Profile](screenshots/profile.png) | ![Notifications](screenshots/notifications.png) |

### Settings & More
| Settings | Dark Mode | Widget |
|----------|-----------|--------|
| ![Settings](screenshots/settings.png) | ![Dark](screenshots/dark.png) | ![Widget](screenshots/widget.png) |

## 🏗️ Architecture

### MVVM + Coordinator Pattern
```
┌─────────────────────────────────────────┐
│                 Views                   │
│              (SwiftUI)                  │
├─────────────────────────────────────────┤
│              ViewModels                 │
│         (ObservableObject)              │
├─────────────────────────────────────────┤
│               Models                    │
│         (Codable Structs)               │
├─────────────────────────────────────────┤
│              Services                   │
│    (API, Storage, Notifications)        │
├─────────────────────────────────────────┤
│             Coordinators                │
│         (Navigation Logic)              │
└─────────────────────────────────────────┘
```

### Project Structure
```
BirJobApp/
├── App/
│   ├── BirJobApp.swift           # Main app entry point
│   ├── ContentView.swift         # Root content view
│   └── AppDelegate.swift         # App lifecycle management
├── Views/
│   ├── Home/                     # Home screen components
│   ├── Search/                   # Job search interfaces
│   ├── Profile/                  # User profile screens
│   ├── Settings/                 # App settings
│   └── Components/               # Reusable UI components
├── ViewModels/
│   ├── HomeViewModel.swift       # Home screen logic
│   ├── SearchViewModel.swift     # Search functionality
│   ├── JobViewModel.swift        # Job details logic
│   └── ProfileViewModel.swift    # Profile management
├── Models/
│   ├── Job.swift                 # Job data model
│   ├── User.swift                # User data model
│   ├── APIResponse.swift         # API response models
│   └── AppConfig.swift           # App configuration
├── Services/
│   ├── APIService.swift          # Backend API integration
│   ├── NotificationService.swift # Push notifications
│   ├── StorageService.swift      # Local data storage
│   ├── AnalyticsService.swift    # Usage analytics
│   └── LocationService.swift     # Location services
├── Utilities/
│   ├── Constants.swift           # App constants
│   ├── Extensions/               # Swift extensions
│   ├── Helpers/                  # Utility functions
│   └── Networking/               # Network utilities
├── Resources/
│   ├── Assets.xcassets           # Images and icons
│   ├── Localizable.strings       # Localization
│   └── Info.plist               # App information
└── Supporting Files/
    ├── GoogleService-Info.plist  # Firebase configuration
    └── BirJob.entitlements       # App capabilities
```

## 📋 Requirements

### System Requirements
- **iOS**: 15.0 or later
- **Xcode**: 15.0 or later
- **Swift**: 5.8 or later
- **macOS**: 13.0 or later (for development)

### Development Tools
- **Xcode** 15.0+
- **Swift Package Manager** (built-in)
- **CocoaPods** 1.12+ (optional)
- **Git** 2.30+

### Backend Dependencies
- **BirJob Backend API**: [https://github.com/Ismat-Samadov/birJobBackend](https://github.com/Ismat-Samadov/birJobBackend)
- **API Base URL**: `https://birjobbackend.onrender.com/api/v1`

### Third-Party Services
- **Firebase** (Push notifications)
- **Apple Push Notification Service** (APNs)
- **TestFlight** (Beta distribution)

## 🚀 Installation

### 1. Prerequisites Setup

#### Install Xcode
```bash
# Download from Mac App Store or Apple Developer
# https://developer.apple.com/xcode/

# Verify installation
xcode-select --version
```

#### Install Command Line Tools
```bash
xcode-select --install
```

#### Install CocoaPods (if using)
```bash
sudo gem install cocoapods
pod --version
```

### 2. Clone Repository

```bash
# Clone the repository
git clone https://github.com/Ismat-Samadov/birJobApp.git
cd birJobApp

# Switch to development branch (if needed)
git checkout develop
```

### 3. Install Dependencies

#### Option A: Swift Package Manager (Recommended)
```bash
# Open project in Xcode
open BirJobApp.xcodeproj

# Xcode will automatically resolve Swift Package dependencies
# File -> Package Dependencies -> Resolve Package Versions
```

#### Option B: CocoaPods
```bash
# Install pods
pod install

# Open workspace instead of project
open BirJobApp.xcworkspace
```

### 4. Configuration Setup

#### Create Configuration Files
```bash
# Copy configuration template
cp Config/Config.template.swift Config/Config.swift

# Edit configuration with your values
open Config/Config.swift
```

#### Configure Firebase
1. Download `GoogleService-Info.plist` from Firebase Console
2. Add to Xcode project (drag & drop into project navigator)
3. Ensure it's added to target membership

#### Configure Apple Developer Account
1. Open project settings in Xcode
2. Select "Signing & Capabilities" tab
3. Set your Team and Bundle Identifier
4. Enable required capabilities (Push Notifications, Background App Refresh)

### 5. Build and Run

```bash
# Build project
⌘ + B

# Run on simulator
⌘ + R

# Run on device
# Connect iPhone via USB or wirelessly
# Select device in Xcode and press ⌘ + R
```

## ⚙️ Configuration

### App Configuration

#### Config.swift
```swift
import Foundation

struct Config {
    // MARK: - API Configuration
    static let apiBaseURL = "https://birjobbackend.onrender.com/api/v1"
    static let apiTimeout: TimeInterval = 30.0
    static let maxRetryAttempts = 3
    
    // MARK: - App Information
    static let appName = "BirJob"
    static let appVersion = Bundle.main.infoDictionary?["CFBundleShortVersionString"] as? String ?? "1.0.0"
    static let buildNumber = Bundle.main.infoDictionary?["CFBundleVersion"] as? String ?? "1"
    
    // MARK: - Feature Flags
    static let enablePushNotifications = true
    static let enableAnalytics = true
    static let enableOfflineMode = true
    static let enableDarkMode = true
    
    // MARK: - UI Configuration
    static let jobsPerPage = 20
    static let maxSearchHistory = 50
    static let maxSavedJobs = 100
    static let refreshInterval: TimeInterval = 300 // 5 minutes
    
    // MARK: - Notification Configuration
    static let notificationCategories = [
        "job_alert",
        "application_update",
        "general"
    ]
    
    // MARK: - Environment
    #if DEBUG
    static let isDebug = true
    static let logLevel = "debug"
    #else
    static let isDebug = false
    static let logLevel = "info"
    #endif
}
```

### Info.plist Configuration

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <!-- App Information -->
    <key>CFBundleDisplayName</key>
    <string>BirJob</string>
    <key>CFBundleIdentifier</key>
    <string>com.birjob.app</string>
    <key>CFBundleVersion</key>
    <string>1.0.0</string>
    
    <!-- Permissions -->
    <key>NSUserNotificationsUsageDescription</key>
    <string>BirJob needs notification permission to send you job alerts and updates.</string>
    
    <key>NSLocationWhenInUseUsageDescription</key>
    <string>BirJob uses your location to find relevant job opportunities in your area.</string>
    
    <!-- URL Schemes -->
    <key>CFBundleURLTypes</key>
    <array>
        <dict>
            <key>CFBundleURLName</key>
            <string>com.birjob.app</string>
            <key>CFBundleURLSchemes</key>
            <array>
                <string>birjob</string>
            </array>
        </dict>
    </array>
    
    <!-- Background Modes -->
    <key>UIBackgroundModes</key>
    <array>
        <string>remote-notification</string>
        <string>background-fetch</string>
    </array>
    
    <!-- App Transport Security -->
    <key>NSAppTransportSecurity</key>
    <dict>
        <key>NSAllowsArbitraryLoads</key>
        <false/>
        <key>NSExceptionDomains</key>
        <dict>
            <key>birjobbackend.onrender.com</key>
            <dict>
                <key>NSExceptionAllowsInsecureHTTPLoads</key>
                <false/>
                <key>NSExceptionRequiresForwardSecrecy</key>
                <false/>
            </dict>
        </dict>
    </dict>
</dict>
</plist>
```

### Entitlements Configuration

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <!-- Push Notifications -->
    <key>aps-environment</key>
    <string>development</string> <!-- Change to 'production' for App Store builds -->
    
    <!-- Keychain Sharing -->
    <key>keychain-access-groups</key>
    <array>
        <string>$(AppIdentifierPrefix)com.birjob.app</string>
    </array>
    
    <!-- Associated Domains -->
    <key>com.apple.developer.associated-domains</key>
    <array>
        <string>applinks:birjob.az</string>
    </array>
</dict>
</plist>
```

## 🔌 API Integration

### APIService Implementation

#### APIService.swift
```swift
import Foundation
import Combine

class APIService: ObservableObject {
    static let shared = APIService()
    
    private let baseURL = Config.apiBaseURL
    private let session = URLSession.shared
    private var cancellables = Set<AnyCancellable>()
    
    // MARK: - Job APIs
    
    func fetchJobs(page: Int = 1, limit: Int = 20, search: String? = nil) -> AnyPublisher<JobsResponse, APIError> {
        var components = URLComponents(string: "\(baseURL)/jobs")!
        components.queryItems = [
            URLQueryItem(name: "page", value: "\(page)"),
            URLQueryItem(name: "limit", value: "\(limit)")
        ]
        
        if let search = search, !search.isEmpty {
            components.queryItems?.append(URLQueryItem(name: "search", value: search))
        }
        
        return performRequest(url: components.url!)
    }
    
    func fetchJobDetails(id: Int) -> AnyPublisher<JobDetailResponse, APIError> {
        let url = URL(string: "\(baseURL)/jobs/\(id)")!
        return performRequest(url: url)
    }
    
    func fetchFeaturedJobs(userEmail: String? = nil) -> AnyPublisher<FeaturedJobsResponse, APIError> {
        var components = URLComponents(string: "\(baseURL)/mobile/jobs/featured")!
        components.queryItems = [URLQueryItem(name: "limit", value: "10")]
        
        if let email = userEmail {
            components.queryItems?.append(URLQueryItem(name: "userEmail", value: email))
        }
        
        return performRequest(url: components.url!)
    }
    
    // MARK: - User APIs
    
    func registerUser(email: String) -> AnyPublisher<UserResponse, APIError> {
        let url = URL(string: "\(baseURL)/users/register")!
        let body = ["email": email]
        return performRequest(url: url, method: "POST", body: body)
    }
    
    func fetchUserProfile(email: String) -> AnyPublisher<UserProfileResponse, APIError> {
        var components = URLComponents(string: "\(baseURL)/users/profile")!
        components.queryItems = [URLQueryItem(name: "email", value: email)]
        return performRequest(url: components.url!)
    }
    
    func addKeyword(email: String, keyword: String) -> AnyPublisher<KeywordResponse, APIError> {
        let url = URL(string: "\(baseURL)/users/keywords")!
        let body = ["email": email, "keyword": keyword]
        return performRequest(url: url, method: "POST", body: body)
    }
    
    func removeKeyword(email: String, keyword: String) -> AnyPublisher<EmptyResponse, APIError> {
        let url = URL(string: "\(baseURL)/users/keywords")!
        let body = ["email": email, "keyword": keyword]
        return performRequest(url: url, method: "DELETE", body: body)
    }
    
    // MARK: - Notification APIs
    
    func registerDevice(email: String, deviceToken: String, platform: String = "ios") -> AnyPublisher<DeviceRegistrationResponse, APIError> {
        let url = URL(string: "\(baseURL)/notifications/register-device")!
        let body: [String: Any] = [
            "email": email,
            "deviceToken": deviceToken,
            "platform": platform,
            "appVersion": Config.appVersion,
            "deviceModel": UIDevice.current.model
        ]
        return performRequest(url: url, method: "POST", body: body)
    }
    
    // MARK: - Analytics APIs
    
    func logAppLaunch(isFirstLaunch: Bool = false) -> AnyPublisher<EmptyResponse, APIError> {
        let url = URL(string: "\(baseURL)/mobile/app-launch")!
        let body: [String: Any] = [
            "platform": "ios",
            "appVersion": Config.appVersion,
            "buildNumber": Config.buildNumber,
            "deviceModel": UIDevice.current.model,
            "osVersion": UIDevice.current.systemVersion,
            "isFirstLaunch": isFirstLaunch,
            "sessionId": UUID().uuidString
        ]
        return performRequest(url: url, method: "POST", body: body)
    }
    
    func logSearch(query: String, resultCount: Int) -> AnyPublisher<EmptyResponse, APIError> {
        let url = URL(string: "\(baseURL)/analytics/search")!
        let body: [String: Any] = [
            "query": query,
            "resultCount": resultCount,
            "searchDuration": 0,
            "clickedResult": false,
            "deviceType": "mobile",
            "sessionId": UUID().uuidString,
            "searchSource": "ios"
        ]
        return performRequest(url: url, method: "POST", body: body)
    }
    
    // MARK: - Private Methods
    
    private func performRequest<T: Codable>(
        url: URL,
        method: String = "GET",
        body: [String: Any]? = nil
    ) -> AnyPublisher<T, APIError> {
        var request = URLRequest(url: url)
        request.httpMethod = method
        request.setValue("application/json", forHTTPHeaderField: "Content-Type")
        request.setValue("BirJob iOS/\(Config.appVersion)", forHTTPHeaderField: "User-Agent")
        request.timeoutInterval = Config.apiTimeout
        
        if let body = body {
            do {
                request.httpBody = try JSONSerialization.data(withJSONObject: body)
            } catch {
                return Fail(error: APIError.encodingError)
                    .eraseToAnyPublisher()
            }
        }
        
        return session.dataTaskPublisher(for: request)
            .tryMap { data, response -> Data in
                guard let httpResponse = response as? HTTPURLResponse else {
                    throw APIError.invalidResponse
                }
                
                guard 200...299 ~= httpResponse.statusCode else {
                    throw APIError.httpError(httpResponse.statusCode)
                }
                
                return data
            }
            .decode(type: T.self, decoder: JSONDecoder())
            .mapError { error in
                if error is DecodingError {
                    return APIError.decodingError
                } else if let apiError = error as? APIError {
                    return apiError
                } else {
                    return APIError.networkError(error)
                }
            }
            .receive(on: DispatchQueue.main)
            .eraseToAnyPublisher()
    }
}

// MARK: - API Error Types

enum APIError: Error, LocalizedError {
    case invalidURL
    case invalidResponse
    case encodingError
    case decodingError
    case networkError(Error)
    case httpError(Int)
    
    var errorDescription: String? {
        switch self {
        case .invalidURL:
            return "Invalid URL"
        case .invalidResponse:
            return "Invalid response"
        case .encodingError:
            return "Encoding error"
        case .decodingError:
            return "Decoding error"
        case .networkError(let error):
            return "Network error: \(error.localizedDescription)"
        case .httpError(let code):
            return "HTTP error: \(code)"
        }
    }
}
```

### Data Models

#### Job.swift
```swift
import Foundation

// MARK: - Job Models

struct Job: Codable, Identifiable, Hashable {
    let id: Int
    let title: String
    let company: String
    let applyLink: String
    let source: String?
    let postedAt: Date
    let postedRelative: String?
    
    enum CodingKeys: String, CodingKey {
        case id, title, company, source
        case applyLink
        case postedAt
        case postedRelative
    }
}

struct JobsResponse: Codable {
    let success: Bool
    let data: JobsData
    let cached: Bool
    let timestamp: Date
}

struct JobsData: Codable {
    let jobs: [Job]
    let metadata: JobsMetadata
    let sources: [JobSource]
    let topCompanies: [TopCompany]
    let lastUpdated: Date?
}

struct JobsMetadata: Codable {
    let totalJobs: Int
    let currentPage: Int
    let totalPages: Int
    let hasNextPage: Bool
    let hasPreviousPage: Bool
    let itemsPerPage: Int
}

struct JobSource: Codable, Identifiable {
    var id: String { name }
    let name: String
    let count: Int
}

struct TopCompany: Codable, Identifiable {
    var id: String { name }
    let name: String
    let count: Int
}

// MARK: - Job Detail Models

struct JobDetailResponse: Codable {
    let success: Bool
    let data: JobDetailData
}

struct JobDetailData: Codable {
    let job: Job
    let similarJobs: [SimilarJob]
    let company: CompanyInfo
}

struct SimilarJob: Codable, Identifiable {
    let id: Int
    let title: String
    let postedAt: Date
    let postedRelative: String
}

struct CompanyInfo: Codable {
    let name: String
    let totalJobs: Int
}

// MARK: - Featured Jobs Models

struct FeaturedJobsResponse: Codable {
    let success: Bool
    let data: FeaturedJobsData
}

struct FeaturedJobsData: Codable {
    let jobs: [FeaturedJob]
    let metadata: FeaturedJobsMetadata
}

struct FeaturedJob: Codable, Identifiable {
    let id: Int
    let title: String
    let company: String
    let applyLink: String
    let source: String?
    let postedAt: Date
    let postedRelative: String
    let isFeatured: Bool
    let matchReason: String
}

struct FeaturedJobsMetadata: Codable {
    let totalJobs: Int
    let isPersonalized: Bool
    let lastUpdated: Date
}
```

#### User.swift
```swift
import Foundation

// MARK: - User Models

struct User: Codable, Identifiable {
    let id: Int
    let email: String
    let memberSince: Date
    let lastNotified: Date?
    
    enum CodingKeys: String, CodingKey {
        case id, email
        case memberSince = "createdAt"
        case lastNotified = "lastNotifiedAt"
    }
}

struct UserResponse: Codable {
    let success: Bool
    let data: UserData
    let message: String
    let timestamp: Date
}

struct UserData: Codable {
    let user: User
}

// MARK: - User Profile Models

struct UserProfileResponse: Codable {
    let success: Bool
    let data: UserProfile
    let cached: Bool
    let timestamp: Date
}

struct UserProfile: Codable {
    let user: User
    let keywords: [Keyword]
    let sourcePreferences: [SourcePreference]
    let recentNotifications: [RecentNotification]
    let stats: UserStats
}

struct Keyword: Codable, Identifiable {
    let id: Int
    let keyword: String
    let addedAt: Date
}

struct SourcePreference: Codable, Identifiable {
    let id: Int
    let source: String
    let addedAt: Date
}

struct RecentNotification: Codable, Identifiable {
    let id: Int
    let sentAt: Date
    let isRead: Bool
    let matchedKeyword: String
}

struct UserStats: Codable {
    let totalKeywords: Int
    let totalSources: Int
    let totalNotifications: Int
    let unreadNotifications: Int
}

// MARK: - Keyword Management

struct KeywordResponse: Codable {
    let success: Bool
    let data: KeywordData
    let message: String
    let timestamp: Date
}

struct KeywordData: Codable {
    let keyword: KeywordInfo
}

struct KeywordInfo: Codable {
    let id: Int
    let keyword: String
    let addedAt: Date
}

// MARK: - Device Registration

struct DeviceRegistrationResponse: Codable {
    let success: Bool
    let data: DeviceRegistrationData
    let message: String
    let timestamp: Date
}

struct DeviceRegistrationData: Codable {
    let deviceRegistered: Bool
    let platform: String
    let registeredAt: String
}

// MARK: - Empty Response

struct EmptyResponse: Codable {
    let success: Bool
    let message: String?
    let timestamp: Date
}
```

## 🔔 Push Notifications

### NotificationService Implementation

#### NotificationService.swift
```swift
import UserNotifications
import UIKit
import Combine

class NotificationService: NSObject, ObservableObject {
    static let shared = NotificationService()
    
    @Published var isAuthorized = false
    @Published var deviceToken: String?
    
    private var cancellables = Set<AnyCancellable>()
    
    override init() {
        super.init()
        checkAuthorizationStatus()
    }
    
    // MARK: - Authorization
    
    func requestAuthorization() {
        UNUserNotificationCenter.current().requestAuthorization(options: [.alert, .badge, .sound]) { [weak self] granted, error in
            DispatchQueue.main.async {
                self?.isAuthorized = granted
                if granted {
                    self?.registerForRemoteNotifications()
                }
            }
        }
    }
    
    private func checkAuthorizationStatus() {
        UNUserNotificationCenter.current().getNotificationSettings { [weak self] settings in
            DispatchQueue.main.async {
                self?.isAuthorized = settings.authorizationStatus == .authorized
            }
        }
    }
    
    // MARK: - Device Token Management
    
    private func registerForRemoteNotifications() {
        DispatchQueue.main.async {
            UIApplication.shared.registerForRemoteNotifications()
        }
    }
    
    func didRegisterForRemoteNotifications(withDeviceToken deviceToken: Data) {
        let tokenString = deviceToken.map { String(format: "%02.2hhx", $0) }.joined()
        self.deviceToken = tokenString
        
        // Register device with backend
        if let userEmail = UserDefaults.standard.string(forKey: "userEmail") {
            registerDeviceWithBackend(email: userEmail, deviceToken: tokenString)
        }
    }
    
    func didFailToRegisterForRemoteNotifications(withError error: Error) {
        print("Failed to register for remote notifications: \(error)")
    }
    
    // MARK: - Backend Integration
    
    private func registerDeviceWithBackend(email: String, deviceToken: String) {
        APIService.shared.registerDevice(email: email, deviceToken: deviceToken)
            .sink(
                receiveCompletion: { completion in
                    if case .failure(let error) = completion {
                        print("Failed to register device: \(error)")
                    }
                },
                receiveValue: { response in
                    print("Device registered successfully: \(response)")
                }
            )
            .store(in: &cancellables)
    }
    
    // MARK: - Notification Categories
    
    func setupNotificationCategories() {
        let jobAlertAction = UNNotificationAction(
            identifier: "VIEW_JOB",
            title: "View Job",
            options: [.foreground]
        )
        
        let dismissAction = UNNotificationAction(
            identifier: "DISMISS",
            title: "Dismiss",
            options: []
        )
        
        let jobAlertCategory = UNNotificationCategory(
            identifier: "job_alert",
            actions: [jobAlertAction, dismissAction],
            intentIdentifiers: [],
            options: []
        )
        
        UNUserNotificationCenter.current().setNotificationCategories([jobAlertCategory])
    }
    
    // MARK: - Local Notifications
    
    func scheduleLocalNotification(title: String, body: String, userInfo: [String: Any] = [:]) {
        let content = UNMutableNotificationContent()
        content.title = title
        content.body = body
        content.sound = .default
        content.userInfo = userInfo
        
        let trigger = UNTimeIntervalNotificationTrigger(timeInterval: 1, repeats: false)
        let request = UNNotificationRequest(identifier: UUID().uuidString, content: content, trigger: trigger)
        
        UNUserNotificationCenter.current().add(request) { error in
            if let error = error {
                print("Error scheduling local notification: \(error)")
            }
        }
    }
}

// MARK: - UNUserNotificationCenterDelegate

extension NotificationService: UNUserNotificationCenterDelegate {
    
    func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
        // Show notification even when app is in foreground
        completionHandler([.alert, .badge, .sound])
    }
    
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        
        let userInfo = response.notification.request.content.userInfo
        
        switch response.actionIdentifier {
        case "VIEW_JOB":
            handleViewJobAction(userInfo: userInfo)
        case UNNotificationDefaultActionIdentifier:
            handleDefaultAction(userInfo: userInfo)
        case "DISMISS":
            break
        default:
            break
        }
        
        completionHandler()
    }
    
    private func handleViewJobAction(userInfo: [AnyHashable: Any]) {
        if let jobIdString = userInfo["jobId"] as? String,
           let jobId = Int(jobIdString) {
            // Navigate to job details
            NotificationCenter.default.post(name: .navigateToJob, object: jobId)
        }
    }
    
    private func handleDefaultAction(userInfo: [AnyHashable: Any]) {
        if let type = userInfo["type"] as? String {
            switch type {
            case "job_alert":
                // Navigate to jobs list
                NotificationCenter.default.post(name: .navigateToJobs, object: nil)
            default:
                break
            }
        }
    }
}

// MARK: - Notification Names

extension Notification.Name {
    static let navigateToJob = Notification.Name("navigateToJob")
    static let navigateToJobs = Notification.Name("navigateToJobs")
}
```

### AppDelegate Integration

#### AppDelegate.swift
```swift
import UIKit
import UserNotifications
import Firebase

class AppDelegate: NSObject, UIApplicationDelegate {
    
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil) -> Bool {
        
        // Configure Firebase
        FirebaseApp.configure()
        
        // Setup notification center
        UNUserNotificationCenter.current().delegate = NotificationService.shared
        NotificationService.shared.setupNotificationCategories()
        
        // Log app launch
        APIService.shared.logAppLaunch(isFirstLaunch: isFirstLaunch())
            .sink(receiveCompletion: { _ in }, receiveValue: { _ in })
            .store(in: &cancellables)
        
        return true
    }
    
    func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
        NotificationService.shared.didRegisterForRemoteNotifications(withDeviceToken: deviceToken)
    }
    
    func application(_ application: UIApplication, didFailToRegisterForRemoteNotificationsWithError error: Error) {
        NotificationService.shared.didFailToRegisterForRemoteNotifications(withError: error)
    }
    
    private func isFirstLaunch() -> Bool {
        let hasLaunchedBefore = UserDefaults.standard.bool(forKey: "hasLaunchedBefore")
        if !hasLaunchedBefore {
            UserDefaults.standard.set(true, forKey: "hasLaunchedBefore")
            return true
        }
        return false
    }
    
    private var cancellables = Set<AnyCancellable>()
}
```

## 🛠️ Development

### Development Workflow

#### 1. Setup Development Environment
```bash
# Clone repository
git clone https://github.com/Ismat-Samadov/birJobApp.git
cd birJobApp

# Open in Xcode
open BirJobApp.xcodeproj

# Install dependencies (if using CocoaPods)
pod install
open BirJobApp.xcworkspace
```

#### 2. Branch Strategy
```bash
# Main branches
main        # Production releases
develop     # Development integration
staging     # Staging builds

# Feature branches
feature/job-search-improvements
feature/push-notification-enhancements
feature/offline-mode

# Bug fix branches
bugfix/search-crash-fix
bugfix/notification-not-showing

# Release branches
release/1.1.0
```

#### 3. Development Best Practices

**SwiftUI Development:**
```swift
// Use @StateObject for ViewModels
struct JobListView: View {
    @StateObject private var viewModel = JobListViewModel()
    
    var body: some View {
        NavigationView {
            List(viewModel.jobs) { job in
                JobRowView(job: job)
                    .onTapGesture {
                        viewModel.selectJob(job)
                    }
            }
            .onAppear {
                viewModel.loadJobs()
            }
        }
    }
}

// Separate concerns with ViewModels
class JobListViewModel: ObservableObject {
    @Published var jobs: [Job] = []
    @Published var isLoading = false
    @Published var errorMessage: String?
    
    private let apiService = APIService.shared
    private var cancellables = Set<AnyCancellable>()
    
    func loadJobs() {
        isLoading = true
        
        apiService.fetchJobs()
            .sink(
                receiveCompletion: { [weak self] completion in
                    self?.isLoading = false
                    if case .failure(let error) = completion {
                        self?.errorMessage = error.localizedDescription
                    }
                },
                receiveValue: { [weak self] response in
                    self?.jobs = response.data.jobs
                }
            )
            .store(in: &cancellables)
    }
}
```

**Error Handling:**
```swift
// Consistent error handling across the app
struct ErrorView: View {
    let error: Error
    let retry: () -> Void
    
    var body: some View {
        VStack(spacing: 16) {
            Image(systemName: "exclamationmark.triangle")
                .font(.largeTitle)
                .foregroundColor(.orange)
            
            Text("Something went wrong")
                .font(.headline)
            
            Text(error.localizedDescription)
                .font(.body)
                .multilineTextAlignment(.center)
                .foregroundColor(.secondary)
            
            Button("Try Again") {
                retry()
            }
            .buttonStyle(.borderedProminent)
        }
        .padding()
    }
}
```

**Loading States:**
```swift
// Consistent loading indicators
struct LoadingView: View {
    let message: String
    
    var body: some View {
        VStack(spacing: 16) {
            ProgressView()
                .scaleEffect(1.2)
            
            Text(message)
                .font(.body)
                .foregroundColor(.secondary)
        }
        .frame(maxWidth: .infinity, maxHeight: .infinity)
        .background(Color(.systemBackground))
    }
}
```

#### 4. Code Organization

**Feature-based Structure:**
```
Views/
├── Home/
│   ├── HomeView.swift
│   ├── FeaturedJobsView.swift
│   └── QuickSearchView.swift
├── Search/
│   ├── SearchView.swift
│   ├── SearchResultsView.swift
│   ├── FilterView.swift
│   └── SearchHistoryView.swift
├── JobDetail/
│   ├── JobDetailView.swift
│   ├── SimilarJobsView.swift
│   └── ApplyView.swift
└── Profile/
    ├── ProfileView.swift
    ├── KeywordsView.swift
    ├── SettingsView.swift
    └── NotificationsView.swift
```

**ViewModels Structure:**
```
ViewModels/
├── HomeViewModel.swift
├── SearchViewModel.swift
├── JobDetailViewModel.swift
├── ProfileViewModel.swift
└── Base/
    ├── BaseViewModel.swift
    └── LoadingState.swift
```

### Debugging and Testing

#### Debug Configuration
```swift
// Debug utilities
#if DEBUG
extension View {
    func debugPrint(_ value: Any) -> some View {
        print("🐛 Debug:", value)
        return self
    }
    
    func debugBorder(_ color: Color = .red) -> some View {
        self.border(color, width: 1)
    }
}
#endif

// API debugging
class APIService {
    private func logRequest(_ request: URLRequest) {
        #if DEBUG
        print("🌐 API Request: \(request.httpMethod ?? "GET") \(request.url?.absoluteString ?? "")")
        if let body = request.httpBody,
           let bodyString = String(data: body, encoding: .utf8) {
            print("📤 Request Body: \(bodyString)")
        }
        #endif
    }
    
    private func logResponse(_ data: Data, _ response: URLResponse) {
        #if DEBUG
        if let httpResponse = response as? HTTPURLResponse {
            print("📥 API Response: \(httpResponse.statusCode)")
        }
        if let responseString = String(data: data, encoding: .utf8) {
            print("📄 Response Body: \(responseString)")
        }
        #endif
    }
}
```

#### Unit Testing
```swift
import XCTest
import Combine
@testable import BirJobApp

class APIServiceTests: XCTestCase {
    var apiService: APIService!
    var cancellables: Set<AnyCancellable>!
    
    override func setUp() {
        super.setUp()
        apiService = APIService()
        cancellables = Set<AnyCancellable>()
    }
    
    override func tearDown() {
        cancellables = nil
        apiService = nil
        super.tearDown()
    }
    
    func testFetchJobs() {
        let expectation = XCTestExpectation(description: "Fetch jobs")
        
        apiService.fetchJobs()
            .sink(
                receiveCompletion: { completion in
                    if case .failure(let error) = completion {
                        XCTFail("Expected success, got error: \(error)")
                    }
                },
                receiveValue: { response in
                    XCTAssertTrue(response.success)
                    XCTAssertFalse(response.data.jobs.isEmpty)
                    expectation.fulfill()
                }
            )
            .store(in: &cancellables)
        
        wait(for: [expectation], timeout: 10.0)
    }
}
```

#### UI Testing
```swift
import XCTest

class BirJobUITests: XCTestCase {
    var app: XCUIApplication!
    
    override func setUp() {
        super.setUp()
        app = XCUIApplication()
        app.launch()
    }
    
    func testJobSearch() {
        // Test search functionality
        let searchField = app.searchFields["Search jobs..."]
        XCTAssertTrue(searchField.exists)
        
        searchField.tap()
        searchField.typeText("software engineer")
        
        app.keyboards.buttons["Search"].tap()
        
        // Wait for results
        let firstJob = app.cells.firstMatch
        XCTAssertTrue(firstJob.waitForExistence(timeout: 5))
        
        // Tap on first job
        firstJob.tap()
        
        // Verify job detail view
        let jobTitle = app.staticTexts["jobTitle"]
        XCTAssertTrue(jobTitle.waitForExistence(timeout: 3))
    }
    
    func testNotificationPermission() {
        // Test notification permission flow
        let settingsTab = app.tabBars.buttons["Settings"]
        settingsTab.tap()
        
        let notificationToggle = app.switches["enableNotifications"]
        if notificationToggle.exists && notificationToggle.value as? String == "0" {
            notificationToggle.tap()
            
            // Handle system permission alert
            let allowButton = app.alerts.buttons["Allow"]
            if allowButton.waitForExistence(timeout: 3) {
                allowButton.tap()
            }
        }
    }
}
```

### Performance Optimization

#### Memory Management
```swift
// Use weak references to avoid retain cycles
class JobDetailViewModel: ObservableObject {
    @Published var job: Job?
    
    private weak var navigationDelegate: NavigationDelegate?
    private var cancellables = Set<AnyCancellable>()
    
    deinit {
        cancellables.removeAll()
    }
}

// Lazy loading for expensive operations
struct JobListView: View {
    @StateObject private var viewModel = JobListViewModel()
    
    var body: some View {
        List {
            ForEach(viewModel.jobs) { job in
                JobRowView(job: job)
                    .onAppear {
                        if viewModel.shouldLoadMore(for: job) {
                            viewModel.loadMoreJobs()
                        }
                    }
            }
        }
    }
}
```

#### Image Caching
```swift
import SwiftUI

// Custom AsyncImage with caching
struct CachedAsyncImage<Content: View>: View {
    private let url: URL?
    private let content: (AsyncImagePhase) -> Content
    
    init(url: URL?, @ViewBuilder content: @escaping (AsyncImagePhase) -> Content) {
        self.url = url
        self.content = content
    }
    
    var body: some View {
        AsyncImage(url: url) { phase in
            content(phase)
        }
        .id(url?.absoluteString) // Cache by URL
    }
}

// Usage
CachedAsyncImage(url: URL(string: company.logoURL)) { phase in
    switch phase {
    case .success(let image):
        image
            .resizable()
            .aspectRatio(contentMode: .fit)
    case .failure(_):
        Image(systemName: "building.2")
            .foregroundColor(.gray)
    case .empty:
        ProgressView()
    @unknown default:
        EmptyView()
    }
}
.frame(width: 40, height: 40)
```

## 🧪 Testing

### Unit Testing Setup

#### Test Target Configuration
```swift
// BirJobAppTests.swift
import XCTest
import Combine
@testable import BirJobApp

class BirJobAppTests: XCTestCase {
    
    override func setUpWithError() throws {
        // Set up test environment
        continueAfterFailure = false
    }
    
    override func tearDownWithError() throws {
        // Clean up after tests
    }
    
    // Test example
    func testJobModelDecoding() throws {
        let jsonData = """
        {
            "id": 1,
            "title": "iOS Developer",
            "company": "Tech Company",
            "applyLink": "https://example.com/apply",
            "source": "LinkedIn",
            "postedAt": "2025-05-28T10:00:00Z",
            "postedRelative": "2 hours ago"
        }
        """.data(using: .utf8)!
        
        let decoder = JSONDecoder()
        decoder.dateDecodingStrategy = .iso8601
        
        let job = try decoder.decode(Job.self, from: jsonData)
        
        XCTAssertEqual(job.id, 1)
        XCTAssertEqual(job.title, "iOS Developer")
        XCTAssertEqual(job.company, "Tech Company")
    }
}
```

### API Testing

#### Mock API Service
```swift
// MockAPIService.swift
class MockAPIService: APIService {
    var shouldReturnError = false
    var mockJobs: [Job] = []
    
    override func fetchJobs(page: Int = 1, limit: Int = 20, search: String? = nil) -> AnyPublisher<JobsResponse, APIError> {
        if shouldReturnError {
            return Fail(error: APIError.networkError(NSError(domain: "test", code: 1)))
                .eraseToAnyPublisher()
        }
        
        let response = JobsResponse(
            success: true,
            data: JobsData(
                jobs: mockJobs,
                metadata: JobsMetadata(
                    totalJobs: mockJobs.count,
                    currentPage: page,
                    totalPages: 1,
                    hasNextPage: false,
                    hasPreviousPage: false,
                    itemsPerPage: limit
                ),
                sources: [],
                topCompanies: [],
                lastUpdated: Date()
            ),
            cached: false,
            timestamp: Date()
        )
        
        return Just(response)
            .setFailureType(to: APIError.self)
            .eraseToAnyPublisher()
    }
}

// Test using mock service
class JobListViewModelTests: XCTestCase {
    var viewModel: JobListViewModel!
    var mockAPIService: MockAPIService!
    var cancellables: Set<AnyCancellable>!
    
    override func setUp() {
        super.setUp()
        mockAPIService = MockAPIService()
        viewModel = JobListViewModel(apiService: mockAPIService)
        cancellables = Set<AnyCancellable>()
    }
    
    func testLoadJobs() {
        // Given
        let expectedJob = Job(
            id: 1,
            title: "Test Job",
            company: "Test Company",
            applyLink: "https://test.com",
            source: "Test Source",
            postedAt: Date(),
            postedRelative: "1 hour ago"
        )
        mockAPIService.mockJobs = [expectedJob]
        
        let expectation = XCTestExpectation(description: "Jobs loaded")
        
        // When
        viewModel.$jobs
            .dropFirst() // Skip initial empty array
            .sink { jobs in
                // Then
                XCTAssertEqual(jobs.count, 1)
                XCTAssertEqual(jobs.first?.title, "Test Job")
                expectation.fulfill()
            }
            .store(in: &cancellables)
        
        viewModel.loadJobs()
        
        wait(for: [expectation], timeout: 1.0)
    }
}
```

### UI Testing

#### Page Object Pattern
```swift
// PageObjects/HomePage.swift
import XCUITest

struct HomePage {
    let app: XCUIApplication
    
    // Elements
    var searchBar: XCUIElement {
        app.searchFields["Search jobs..."]
    }
    
    var featuredJobsSection: XCUIElement {
        app.scrollViews["featuredJobs"]
    }
    
    var firstFeaturedJob: XCUIElement {
        featuredJobsSection.cells.firstMatch
    }
    
    // Actions
    func searchFor(_ term: String) {
        searchBar.tap()
        searchBar.typeText(term)
        app.keyboards.buttons["Search"].tap()
    }
    
    func tapFirstFeaturedJob() {
        firstFeaturedJob.tap()
    }
    
    // Assertions
    func assertFeaturedJobsVisible() {
        XCTAssertTrue(featuredJobsSection.exists)
        XCTAssertTrue(firstFeaturedJob.exists)
    }
}

// Test using Page Object
class HomePageTests: XCTestCase {
    var app: XCUIApplication!
    var homePage: HomePage!
    
    override func setUp() {
        super.setUp()
        app = XCUIApplication()
        homePage = HomePage(app: app)
        app.launch()
    }
    
    func testJobSearch() {
        // Given
        homePage.assertFeaturedJobsVisible()
        
        // When
        homePage.searchFor("iOS Developer")
        
        // Then
        let searchResults = app.tables["searchResults"]
        XCTAssertTrue(searchResults.waitForExistence(timeout: 5))
    }
}
```

### Integration Testing

#### API Integration Tests
```swift
class APIIntegrationTests: XCTestCase {
    var apiService: APIService!
    var cancellables: Set<AnyCancellable>!
    
    override func setUp() {
        super.setUp()
        apiService = APIService.shared
        cancellables = Set<AnyCancellable>()
    }
    
    func testFullJobSearchFlow() {
        let expectation = XCTestExpectation(description: "Full job search flow")
        expectation.expectedFulfillmentCount = 3
        
        // 1. Fetch jobs
        apiService.fetchJobs(search: "developer")
            .sink(
                receiveCompletion: { completion in
                    if case .failure(let error) = completion {
                        XCTFail("Job search failed: \(error)")
                    }
                },
                receiveValue: { response in
                    XCTAssertTrue(response.success)
                    XCTAssertFalse(response.data.jobs.isEmpty)
                    expectation.fulfill()
                    
                    // 2. Get first job details
                    let firstJob = response.data.jobs.first!
                    self.apiService.fetchJobDetails(id: firstJob.id)
                        .sink(
                            receiveCompletion: { completion in
                                if case .failure(let error) = completion {
                                    XCTFail("Job details failed: \(error)")
                                }
                            },
                            receiveValue: { detailResponse in
                                XCTAssertTrue(detailResponse.success)
                                XCTAssertEqual(detailResponse.data.job.id, firstJob.id)
                                expectation.fulfill()
                                
                                // 3. Log search analytics
                                self.apiService.logSearch(query: "developer", resultCount: response.data.jobs.count)
                                    .sink(
                                        receiveCompletion: { completion in
                                            if case .failure(let error) = completion {
                                                XCTFail("Analytics logging failed: \(error)")
                                            }
                                        },
                                        receiveValue: { _ in
                                            expectation.fulfill()
                                        }
                                    )
                                    .store(in: &self.cancellables)
                            }
                        )
                        .store(in: &self.cancellables)
                }
            )
            .store(in: &cancellables)
        
        wait(for: [expectation], timeout: 30.0)
    }
}
```

### Testing Commands

```bash
# Run all tests
⌘ + U

# Run specific test suite
xcodebuild test -scheme BirJobApp -destination 'platform=iOS Simulator,name=iPhone 15,OS=17.0'

# Run only unit tests
xcodebuild test -scheme BirJobApp -destination 'platform=iOS Simulator,name=iPhone 15,OS=17.0' -only-testing:BirJobAppTests

# Run only UI tests
xcodebuild test -scheme BirJobApp -destination 'platform=iOS Simulator,name=iPhone 15,OS=17.0' -only-testing:BirJobAppUITests

# Run tests with code coverage
xcodebuild test -scheme BirJobApp -destination 'platform=iOS Simulator,name=iPhone 15,OS=17.0' -enableCodeCoverage YES
```

## 🚀 Deployment

### App Store Deployment

#### 1. Prepare for Release

**Update Version Information:**
```swift
// In Xcode project settings
// Version: 1.0.0
// Build: 1

// Update Info.plist
<key>CFBundleShortVersionString</key>
<string>1.0.0</string>
<key>CFBundleVersion</key>
<string>1</string>
```

**Update Configuration for Production:**
```swift
// Config.swift
#if DEBUG
static let apiBaseURL = "https://birjobbackend-dev.onrender.com/api/v1"
#else
static let apiBaseURL = "https://birjobbackend.onrender.com/api/v1"
#endif
```

**Update Entitlements:**
```xml
<!-- BirJob.entitlements -->
<key>aps-environment</key>
<string>production</string> <!-- Change from development -->
```

#### 2. Archive and Upload

```bash
# Create archive
# In Xcode: Product → Archive

# Validate archive
# In Organizer: Validate App

# Upload to App Store Connect
# In Organizer: Distribute App → App Store Connect
```

#### 3. TestFlight Beta Testing

**Internal Testing:**
```
1. Upload build to App Store Connect
2. Add internal testers in TestFlight
3. Send invite to testers
4. Collect feedback and crash reports
```

**External Testing:**
```
1. Submit for TestFlight Beta App Review
2. Add external testers (up to 10,000)
3. Distribute beta build
4. Monitor metrics and feedback
```

#### 4. App Store Review

**Prepare App Store Information:**
```
App Name: BirJob
Subtitle: Find Your Dream Job in Azerbaijan
Category: Business
Keywords: job search, career, employment, azerbaijan, birjob
Description: [Detailed app description]
What's New: [Version changelog]
```

**Required Assets:**
```
App Icon: 1024x1024 pixels (PNG, no transparency)
Screenshots:
- iPhone 6.7": 1290x2796 pixels (3 required)
- iPhone 6.5": 1284x2778 pixels (3 required)
- iPhone 5.5": 1242x2208 pixels (3 required)
- iPad Pro (6th Gen): 2048x2732 pixels (3 required)
- iPad Pro (2nd Gen): 2048x2732 pixels (3 required)

App Previews (optional but recommended):
- 30 seconds maximum
- Portrait orientation
- Show key features
```

### Continuous Integration/Deployment

#### GitHub Actions Workflow
```yaml
# .github/workflows/ios.yml
name: iOS Build and Test

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main, develop ]

jobs:
  build:
    runs-on: macos-13
    
    steps:
    - name: Checkout
      uses: actions/checkout@v3
    
    - name: Setup Xcode
      uses: maxim-lobanov/setup-xcode@v1
      with:
        xcode-version: '15.0'
    
    - name: Install dependencies
      run: |
        if [ -f "Podfile" ]; then
          pod install
        fi
    
    - name: Build
      run: |
        xcodebuild -workspace BirJobApp.xcworkspace \
                   -scheme BirJobApp \
                   -destination 'platform=iOS Simulator,name=iPhone 15,OS=17.0' \
                   clean build
    
    - name: Test
      run: |
        xcodebuild -workspace BirJobApp.xcworkspace \
                   -scheme BirJobApp \
                   -destination 'platform=iOS Simulator,name=iPhone 15,OS=17.0' \
                   test
    
    - name: Upload coverage reports
      uses: codecov/codecov-action@v3
      with:
        files: ./coverage.xml
```

#### Fastlane Configuration
```ruby
# Fastfile
platform :ios do
  desc "Run tests"
  lane :test do
    run_tests(
      scheme: "BirJobApp",
      device: "iPhone 15"
    )
  end
  
  desc "Build for TestFlight"
  lane :beta do
    increment_build_number
    build_app(
      scheme: "BirJobApp",
      export_method: "app-store"
    )
    upload_to_testflight
  end
  
  desc "Build and upload to App Store"
  lane :release do
    increment_version_number
    increment_build_number
    build_app(
      scheme: "BirJobApp",
      export_method: "app-store"
    )
    upload_to_app_store(
      submit_for_review: true,
      automatic_release: false
    )
  end
end
```

### Version Management

#### Semantic Versioning
```
Format: MAJOR.MINOR.PATCH

MAJOR: Breaking changes, major new features
MINOR: New features, backward compatible
PATCH: Bug fixes, minor improvements

Examples:
1.0.0 - Initial release
1.1.0 - New search filters
1.1.1 - Bug fixes
2.0.0 - Complete UI redesign
```

#### Release Process
```bash
# 1. Create release branch
git checkout -b release/1.1.0

# 2. Update version numbers
# - Xcode project settings
# - Config.swift
# - README.md

# 3. Update changelog
# CHANGELOG.md

# 4. Test thoroughly
# - Unit tests
# - UI tests
# - Manual testing

# 5. Create archive and upload
# - TestFlight for beta testing
# - App Store for release

# 6. Merge to main
git checkout main
git merge release/1.1.0
git tag v1.1.0
git push origin main --tags
```

## 🔧 Troubleshooting

### Common Issues and Solutions

#### Build Issues

**Issue**: "Could not find module 'Firebase'"
```bash
# Solution: Install Firebase SDK
# 1. Add Firebase to Package Dependencies in Xcode
# 2. Or install via CocoaPods
pod 'Firebase/Analytics'
pod 'Firebase/Messaging'
pod install
```

**Issue**: Code signing errors
```bash
# Solution: Check signing settings
# 1. Open project settings in Xcode
# 2. Go to "Signing & Capabilities"
# 3. Ensure correct Team is selected
# 4. Verify Bundle Identifier is unique
# 5. Check provisioning profiles
```

**Issue**: Build fails with "Module not found"
```bash
# Solution: Clean build folder
# 1. Product → Clean Build Folder (⌘ + Shift + K)
# 2. Delete derived data:
rm -rf ~/Library/Developer/Xcode/DerivedData
# 3. Restart Xcode
```

#### Runtime Issues

**Issue**: API calls failing
```swift
// Debug API issues
#if DEBUG
extension APIService {
    func debugAPICall() {
        let url = URL(string: "\(Config.apiBaseURL)/health")!
        
        URLSession.shared.dataTask(with: url) { data, response, error in
            if let error = error {
                print("❌ API Error: \(error)")
            }
            
            if let httpResponse = response as? HTTPURLResponse {
                print("📊 Status Code: \(httpResponse.statusCode)")
            }
            
            if let data = data,
               let string = String(data: data, encoding: .utf8) {
                print("📝 Response: \(string)")
            }
        }.resume()
    }
}
#endif

// Call in app launch
#if DEBUG
APIService.shared.debugAPICall()
#endif
```

**Issue**: Push notifications not working
```swift
// Debug push notifications
class NotificationService {
    func debugNotificationSetup() {
        #if DEBUG
        print("🔔 Checking notification status...")
        
        UNUserNotificationCenter.current().getNotificationSettings { settings in
            print("Authorization Status: \(settings.authorizationStatus.rawValue)")
            print("Alert Setting: \(settings.alertSetting.rawValue)")
            print("Badge Setting: \(settings.badgeSetting.rawValue)")
            print("Sound Setting: \(settings.soundSetting.rawValue)")
        }
        
        if let deviceToken = self.deviceToken {
            print("📱 Device Token: \(deviceToken)")
        } else {
            print("❌ No device token available")
        }
        #endif
    }
}
```

**Issue**: Data not persisting
```swift
// Debug UserDefaults
extension UserDefaults {
    func debugPrint() {
        #if DEBUG
        print("💾 UserDefaults contents:")
        for (key, value) in self.dictionaryRepresentation() {
            if key.hasPrefix("com.birjob") {
                print("  \(key): \(value)")
            }
        }
        #endif
    }
}

// Call when debugging storage issues
UserDefaults.standard.debugPrint()
```

#### UI Issues

**Issue**: SwiftUI view not updating
```swift
// Ensure proper state management
class JobListViewModel: ObservableObject {
    @Published var jobs: [Job] = [] // ✅ Correct
    
    // Not this:
    // var jobs: [Job] = [] // ❌ Won't trigger UI updates
    
    func updateJobs(_ newJobs: [Job]) {
        // Ensure updates happen on main thread
        DispatchQueue.main.async {
            self.jobs = newJobs
        }
    }
}
```

**Issue**: Navigation not working
```swift
// Use proper navigation patterns
struct ContentView: View {
    @State private var selectedTab = 0
    @State private var navigationPath = NavigationPath()
    
    var body: some View {
        TabView(selection: $selectedTab) {
            NavigationStack(path: $navigationPath) {
                HomeView()
            }
            .tabItem {
                Label("Home", systemImage: "house")
            }
            .tag(0)
        }
        .onReceive(NotificationCenter.default.publisher(for: .navigateToJob)) { notification in
            if let jobId = notification.object as? Int {
                selectedTab = 0 // Switch to home tab
                navigationPath.append(JobDetailDestination(jobId: jobId))
            }
        }
    }
}
```

### Debug Tools

#### Console Logging
```swift
// Structured logging
enum LogLevel: String {
    case debug = "🐛"
    case info = "ℹ️"
    case warning = "⚠️"
    case error = "❌"
}

func log(_ message: String, level: LogLevel = .info, file: String = #file, line: Int = #line) {
    #if DEBUG
    let fileName = URL(fileURLWithPath: file).lastPathComponent
    print("\(level.rawValue) [\(fileName):\(line)] \(message)")
    #endif
}

// Usage
log("API call started", level: .info)
log("Network error occurred", level: .error)
```

#### Memory Debugging
```swift
// Check for memory leaks
class MemoryDebugger {
    static func logMemoryUsage() {
        #if DEBUG
        let memoryUsage = mach_task_basic_info()
        var count = mach_msg_type_number_t(MemoryLayout<mach_task_basic_info>.size)/4
        
        let result: kern_return_t = withUnsafeMutablePointer(to: &memoryUsage) {
            $0.withMemoryRebound(to: integer_t.self, capacity: 1) {
                task_info(mach_task_self_,
                         task_flavor_t(MACH_TASK_BASIC_INFO),
                         $0,
                         &count)
            }
        }
        
        if result == KERN_SUCCESS {
            let usedMB = Float(memoryUsage.resident_size) / 1024.0 / 1024.0
            print("📊 Memory Usage: \(String(format: "%.2f", usedMB)) MB")
        }
        #endif
    }
}

// Call periodically
Timer.scheduledTimer(withTimeInterval: 30.0, repeats: true) { _ in
    MemoryDebugger.logMemoryUsage()
}
```

### Performance Debugging

#### Network Performance
```swift
// Monitor API performance
class APIPerformanceMonitor {
    static func measureAPICall<T>(
        _ apiCall: @escaping () -> AnyPublisher<T, APIError>
    ) -> AnyPublisher<T, APIError> {
        let startTime = CFAbsoluteTimeGetCurrent()
        
        return apiCall()
            .handleEvents(
                receiveCompletion: { _ in
                    let duration = CFAbsoluteTimeGetCurrent() - startTime
                    print("⏱️ API call took \(String(format: "%.3f", duration)) seconds")
                }
            )
            .eraseToAnyPublisher()
    }
}

// Usage
APIPerformanceMonitor.measureAPICall {
    APIService.shared.fetchJobs()
}
```

#### UI Performance
```swift
// Monitor SwiftUI view updates
extension View {
    func debugViewUpdates() -> some View {
        #if DEBUG
        self.onAppear {
            print("🔄 View appeared: \(String(describing: Self.self))")
        }
        .onDisappear {
            print("👋 View disappeared: \(String(describing: Self.self))")
        }
        #else
        self
        #endif
    }
}
```

### Getting Help

When encountering issues:

1. **Check Console Logs**: Look for error messages and warnings
2. **Test on Different Devices**: Issues might be device-specific
3. **Verify API Status**: Check if backend is accessible
4. **Review Recent Changes**: Identify what changed before the issue appeared
5. **Create Minimal Reproduction**: Isolate the problem to specific code
6. **Search Known Issues**: Check GitHub issues and Stack Overflow
7. **Ask for Help**: Create detailed issue reports with:
   - Device information
   - iOS version
   - App version
   - Steps to reproduce
   - Console logs
   - Screenshots/videos

## 🤝 Contributing

We welcome contributions to the BirJob iOS app! Here's how to get involved:

### Getting Started

1. **Fork the Repository**
   ```bash
   # Fork on GitHub, then clone your fork
   git clone https://github.com/YOUR_USERNAME/birJobApp.git
   cd birJobApp
   ```

2. **Set Up Development Environment**
   ```bash
   # Open in Xcode
   open BirJobApp.xcodeproj
   
   # Install dependencies if needed
   pod install
   ```

3. **Create Feature Branch**
   ```bash
   git checkout -b feature/amazing-new-feature
   ```

### Development Guidelines

#### Code Style
- Follow [Swift API Design Guidelines](https://swift.org/documentation/api-design-guidelines/)
- Use **SwiftUI** for all new UI components
- Follow **MVVM** architecture pattern
- Use **Combine** for reactive programming
- Add documentation for public APIs

#### SwiftUI Best Practices
```swift
// ✅ Good: Proper state management
struct JobListView: View {
    @StateObject private var viewModel = JobListViewModel()
    
    var body: some View {
        NavigationView {
            List(viewModel.jobs) { job in
                JobRowView(job: job)
            }
            .onAppear {
                viewModel.loadJobs()
            }
        }
    }
}

// ✅ Good: Extracting reusable components
struct JobRowView: View {
    let job: Job
    
    var body: some View {
        VStack(alignment: .leading, spacing: 8) {
            Text(job.title)
                .font(.headline)
            Text(job.company)
                .font(.subheadline)
                .foregroundColor(.secondary)
        }
        .padding(.vertical, 4)
    }
}

// ❌ Avoid: Massive views
struct MassiveJobView: View {
    var body: some View {
        VStack {
            // 200+ lines of view code
            // Hard to maintain and test
        }
    }
}
```

#### Architecture Patterns
```swift
// ✅ Follow MVVM pattern
class JobListViewModel: ObservableObject {
    @Published var jobs: [Job] = []
    @Published var isLoading = false
    @Published var errorMessage: String?
    
    private let apiService: APIService
    private var cancellables = Set<AnyCancellable>()
    
    init(apiService: APIService = .shared) {
        self.apiService = apiService
    }
    
    func loadJobs() {
        isLoading = true
        
        apiService.fetchJobs()
            .receive(on: DispatchQueue.main)
            .sink(
                receiveCompletion: { [weak self] completion in
                    self?.isLoading = false
                    if case .failure(let error) = completion {
                        self?.errorMessage = error.localizedDescription
                    }
                },
                receiveValue: { [weak self] response in
                    self?.jobs = response.data.jobs
                }
            )
            .store(in: &cancellables)
    }
}
```

### Pull Request Process

1. **Ensure Quality**
   - [ ] Code compiles without warnings
   - [ ] All tests pass
   - [ ] UI looks good on different screen sizes
   - [ ] No memory leaks
   - [ ] Performance is acceptable

2. **Add Tests**
   ```swift
   // Add unit tests for ViewModels
   func testJobListViewModel() {
       let expectation = XCTestExpectation(description: "Jobs loaded")
       
       viewModel.loadJobs()
       
       viewModel.$jobs
           .dropFirst()
           .sink { jobs in
               XCTAssertFalse(jobs.isEmpty)
               expectation.fulfill()
           }
           .store(in: &cancellables)
       
       wait(for: [expectation], timeout: 5.0)
   }
   ```

3. **Update Documentation**
   - Update README if adding new features
   - Add inline documentation for complex code
   - Update API documentation if needed

4. **Create Pull Request**
   ```markdown
   ## Description
   Brief description of changes and motivation.
   
   ## Changes Made
   - [ ] Added new job filtering feature
   - [ ] Improved search performance
   - [ ] Fixed notification bug
   
   ## Testing
   - [ ] Unit tests added/updated
   - [ ] UI tests pass
   - [ ] Manual testing completed
   - [ ] Tested on iPhone and iPad
   
   ## Screenshots
   [Add screenshots showing the changes]
   ```

### Feature Contribution Examples

#### Adding a New Feature
```swift
// 1. Create the View
struct SavedJobsView: View {
    @StateObject private var viewModel = SavedJobsViewModel()
    
    var body: some View {
        NavigationView {
            List {
                ForEach(viewModel.savedJobs) { job in
                    JobRowView(job: job)
                        .swipeActions {
                            Button("Remove") {
                                viewModel.removeSavedJob(job)
                            }
                            .tint(.red)
                        }
                }
            }
            .navigationTitle("Saved Jobs")
            .onAppear {
                viewModel.loadSavedJobs()
            }
        }
    }
}

// 2. Create the ViewModel
class SavedJobsViewModel: ObservableObject {
    @Published var savedJobs: [Job] = []
    
    private let storageService = StorageService.shared
    
    func loadSavedJobs() {
        savedJobs = storageService.getSavedJobs()
    }
    
    func removeSavedJob(_ job: Job) {
        storageService.removeSavedJob(job)
        loadSavedJobs()
    }
}

// 3. Add to main navigation
struct ContentView: View {
    var body: some View {
        TabView {
            // ... other tabs
            
            SavedJobsView()
                .tabItem {
                    Label("Saved", systemImage: "bookmark")
                }
        }
    }
}

// 4. Add tests
class SavedJobsViewModelTests: XCTestCase {
    func testRemoveSavedJob() {
        // Test implementation
    }
}
```

### Issue Reporting

#### Bug Reports
```markdown
**Bug Description**
Clear and concise description of the bug.

**Steps to Reproduce**
1. Go to 'Jobs' tab
2. Search for 'iOS Developer'
3. Tap on first result
4. See error

**Expected Behavior**
Job details should load and display.

**Actual Behavior**
App crashes with error message.

**Environment**
- Device: iPhone 15 Pro
- iOS Version: 17.0
- App Version: 1.0.0

**Screenshots**
[Add screenshots if applicable]

**Console Logs**
```
Error: Thread 1: Fatal error: Index out of range
File: JobDetailView.swift, Line: 45
```
```

#### Feature Requests
```markdown
**Feature Description**
Add ability to filter jobs by salary range.

**Use Case**
As a job seeker, I want to filter jobs by salary so I can find positions within my desired range.

**Proposed Implementation**
- Add salary range slider in filter view
- Update API to support salary filtering
- Add salary display in job listings

**Design Mockups**
[Add UI mockups if available]
```

### Code Review Guidelines

#### For Reviewers
- Focus on code quality, not style preferences
- Test the changes locally when possible
- Provide constructive feedback
- Approve when ready, don't nitpick minor issues

#### For Contributors
- Respond to feedback promptly
- Make requested changes or explain why not
- Keep PR scope focused and small
- Be open to suggestions and learning

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

### Core Technologies
- **[SwiftUI](https://developer.apple.com/xcode/swiftui/)** - Modern UI framework
- **[Combine](https://developer.apple.com/documentation/combine)** - Reactive programming
- **[Firebase](https://firebase.google.com/docs/ios/setup)** - Push notifications and analytics
- **[URLSession](https://developer.apple.com/documentation/foundation/urlsession)** - Networking

### Design Inspiration
- **Apple Human Interface Guidelines**
- **iOS Design Patterns and Best Practices**
- **Leading Job Search Apps UX/UI**

### Special Thanks
- **Backend Team** - For the comprehensive API
- **Beta Testers** - For valuable feedback and bug reports
- **Open Source Community** - For amazing tools and libraries
- **Azerbaijan Job Market** - For the opportunity to serve job seekers

## 📞 Support & Contact

### App Support
- **Email**: support@birjob.az
- **Website**: [https://birjob.az](https://birjob.az)
- **GitHub Issues**: [Report bugs or request features](https://github.com/Ismat-Samadov/birJobApp/issues)

### Development Team
- **Lead Developer**: [Ismat Samadov](https://github.com/Ismat-Samadov)
- **Technical Support**: dev@birjob.az
- **Business Inquiries**: business@birjob.az

### Community
- **LinkedIn**: [BirJob Official](https://linkedin.com/company/birjob)
- **Twitter**: [@birjob_official](https://twitter.com/birjob_official)

---

**Built with ❤️ in Azerbaijan for job seekers everywhere**

🌟 **Star this repository** if you find it useful!
🔄 **Fork and contribute** to make it even better!
📱 **Download BirJob** from the App Store!

---

*Last updated: May 28, 2025*
*Version: 1.0.0*
*Backend API: [BirJob Backend](https://github.com/Ismat-Samadov/birJobBackend)*