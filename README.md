# 🏃 RaceDay Management API

A robust **ASP.NET Core 8 Web API** built for managing sports events (running, walking, cycling), category divisions, participant registrations, and race results. Features role-based cookie authentication, session state tracking, EF Core database persistence, and automated unit testing.

---

## 🛠️ Project Architecture & Tech Stack

* **Framework:** .NET 8.0 (ASP.NET Core Web API)
* **Database & ORM:** Microsoft SQL Server with Entity Framework Core 8.0
* **Authentication & Security:** Cookie-based Authentication, Server-Side Session State, and `IPasswordHasher<T>`
* **Documentation & Testing:** Swashbuckle (Swagger UI), xUnit, Moq, EF Core InMemory Provider

---

## 📋 Core Features & Entity Model

The API enforces strict Role-Based Access Control (**Organiser** vs. **Participant**):

* **Organiser Role:**
  * Create, update, and delete managed events and distance categories.
  * View registrations for managed events.
  * Record and update race results (finish times, positions, split times).
* **Participant Role:**
  * Browse available events and categories.
  * Register/enrol into event categories.
  * View personal registered events and race performance results.

### ERD Entities
1. `Organiser` – Event organiser profiles and credentials.
2. `Participant` – Participant profiles, dates of birth, and contact details.
3. `Event` – Multi-sport event details (Run, Walk, Cycle) and route/weather information.
4. `EventOrganiser` – Composite many-to-many junction linking Organisers to Events.
5. `Category` – Event distance divisions (e.g., 5K, 10K, Half Marathon) with age restrictions.
6. `Registration` – Enrolment record linking a Participant to an Event Category.
7. `Result` – Finish time, overall position, and split times linked 1-to-1 with a Registration.

---

## 🚀 Getting Started

### Prerequisites
* [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
* [SQL Server Express / LocalDB](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
* [Visual Studio 2022](https://visualstudio.microsoft.com/) (with ASP.NET and web development workload) or VS Code

### Installation & Local Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_GITHUB_USERNAME/RaceDay.git](https://github.com/YOUR_GITHUB_USERNAME/RaceDay.git)
   cd RaceDay
