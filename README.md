# Vue.js 3 Components Fundamentals – Exercises

Practical exercises completed as part of the [Vue.js 3 Components Fundamentals with the Options API](https://vueschool.io/courses/vue-js-3-components-fundamentals) course on VueSchool.io.

## Course Overview

The course covers:

- Vue 3 component basics and the Options API
- Component templates and data binding
- Reusable components with **props**
- Nested & globally/locally registered components
- **Custom events** for parent-child communication
- Component naming best practices
- **Lifecycle hooks** (`created`, `mounted`, …)
- **Slots** for flexible component composition

## Exercises

### 1. GitHub User Profile Component

📁 `github-profile-card/index.html`

**Goal:** Build a component that fetches and displays a GitHub user's profile card using the GitHub REST API.

**Concepts practiced:**

| Concept | Where used |
|---|---|
| Props | `:username` passed to each card |
| Custom events | `@remove` emitted to parent |
| Lifecycle hooks | `created()` triggers the API fetch |
| Computed properties | `joinYear` formats the date |
| Conditional rendering | Loading / error / loaded states via `v-if` / `v-else-if` |
| `v-for` list rendering | Parent renders multiple cards |

**Features:**
- Search box to add any GitHub username
- Cards display avatar, name, join year, bio, and follower count
- Remove button emits a custom event to the parent
- Loading spinner and error handling

**GitHub API endpoint used:** `https://api.github.com/users/:username`

---

### 2. Notification Message Component

📁 `notification-component/index.html`

**Goal:** Build a reusable notification/alert component that accepts a message via a slot and a `type` prop (`info`, `success`, `warning`, `error`).

**Concepts practiced:**

| Concept | Where used |
|---|---|
| Props | `type`, `dismissible` |
| Slots | Message body passed as default slot content |
| Custom events | `@dismiss` emitted when the user closes a notification |
| Computed properties | `cssClasses` and `iconName` derived from `type` |
| Conditional rendering | `v-if="visible"` hides the component after dismiss |
| Vue transitions | `<transition name="fade">` for smooth disappearance |

**Features:**
- Four notification types: info, success, warning, error
- Optional dismiss (`×`) button controlled by the `dismissible` prop
- Dynamic CSS classes and icons mapped from the `type` prop
- Parent can programmatically create notifications and listen to dismiss events
- Smooth fade-out animation on close

## How to Run

Both exercises are plain HTML files with no build step required. Just open the file in a browser:

```bash
# Option 1 – Open directly
open github-profile-card/index.html
open notification-component/index.html

# Option 2 – Serve locally (recommended to avoid CORS issues)
npx serve .
# or
python3 -m http.server 8080
```

> **Note:** The GitHub Profile Card exercise fetches data from the public GitHub API. The unauthenticated rate limit is 60 requests/hour per IP. If cards fail to load, wait a moment and refresh.

## Tech Stack

- **Vue 3** (CDN build, Options API)
- **Semantic UI 2.4** (CDN, for styling)
- **Axios** (CDN, for HTTP requests in exercise 1)
- No build tooling required – plain HTML files

## Course Reference

- 🎓 Course: https://vueschool.io/courses/vue-js-3-components-fundamentals
- 📘 Boilerplate (exercise 1): https://github.com/vueschool/vuejs-3-component-fundamentals/commit/fe02bd563c3dd4ae75fb84830049afc99b2be311
- 📘 Boilerplate (exercise 2): https://github.com/vueschool/vuejs-3-component-fundamentals/commit/457d765de6f5df573aab5af6e3650f57b2383f33
