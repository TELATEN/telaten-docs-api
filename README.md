# Telaten API Documentation (Bruno Collection)

This repository contains the API documentation for the **Telaten** project, managed using **Bruno**.

## 📋 Prerequisites

Before using this API collection, ensure you have **Bruno** installed.

1.  **Download Bruno**: Download the latest version from [usebruno.com](https://www.usebruno.com/downloads).
2.  **Install**: Install it according to your operating system.

## 🚀 How to Use

### 1. Import Collection
1.  Open the **Bruno** application.
2.  Click on **"Open Collection"** on the home screen.
3.  Navigate to the folder where you cloned this repository (`telaten-docs-api`).
4.  Click **Open**.

### 2. Environment Setup
This collection uses Environment Variables to easily switch between local and production servers.

1.  In the top right corner of the Bruno app, click the environment dropdown menu (usually labeled `No Environment`).
2.  Select the appropriate environment:
    *   `local`: For localhost development.
    *   `deploy`: For production/staging servers.
    *   `colab`: (If available).

### 3. Authentication
This API uses **Bearer Token Authentication**.
*   Make a request to the **Auth -> Login** endpoint.
*   An automated script (`post-response`) is set up to automatically save the `access_token` from the login response into the environment variable.
*   Other endpoints requiring authentication will automatically use this token.

---

## 📚 Endpoint Documentation

Below is the list of available endpoints in this collection:

### 🔐 Auth
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/auth/register` | Register a new user |
| `POST` | `/auth/login` | Log in and obtain access token |
| `POST` | `/auth/logout` | Log out from the session |
| `POST` | `/auth/refresh-token` | Refresh the access token |
| `GET` | `/auth/me` | Get currently logged-in user info |

### 💼 Business Profile
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/business/profile` | Create a new business profile |
| `GET` | `/business/profile` | Get business profile details |

### 🤖 Chat (AI Assistant)
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/chat/completion` | Send message to AI and get response |
| `GET` | `/chat/sessions` | Get list of chat sessions |
| `GET` | `/chat/history` | Get chat history |
| `DELETE` | `/chat/session/:id` | Delete a chat session |

### 🎯 Milestones
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/milestones` | Get list of milestones |
| `POST` | `/milestones` | Create a new milestone |
| `GET` | `/milestones/:id` | Get milestone details |
| `PUT` | `/milestones/:id` | Update a milestone |
| `POST` | `/milestones/:id/start` | Start a milestone |
| `POST` | `/milestones/task/complete` | Mark a task in milestone as complete |

### 🏆 Gamification

#### User
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/gamification/achievements` | Get list of available achievements |
| `GET` | `/gamification/my-achievements` | Get achievements earned by the user |

#### Admin
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/gamification/achievements` | Create a new achievement |
| `PUT` | `/gamification/achievements/:id` | Update an achievement |
| `DELETE` | `/gamification/achievements/:id` | Delete an achievement |

---
*Created with ❤️ using Bruno*
