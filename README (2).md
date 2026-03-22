# ⚡ Promise Pool

### Async Task Scheduler with Concurrency Control

![Node](https://img.shields.io/badge/node-18%2B-blue)
![Coverage](https://img.shields.io/badge/coverage-95%25-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)

**Run async tasks with concurrency control, retries, and priority ---
all in pure JavaScript.**

------------------------------------------------------------------------

## 🚀 Why This Project?

When you run hundreds of async operations using `Promise.all()`,
everything fires at once:

``` js
await Promise.all(urls.map(url => fetch(url))); // ❌ overloads server
```

This project solves that by introducing: - Controlled concurrency -
Fault tolerance - Smart scheduling

``` js
const pool = new PromisePool(10);
const results = await pool.run(urls.map(url => () => fetch(url))); // ✅ safe
```

------------------------------------------------------------------------

## ✨ Features

-   ⚡ Concurrency Control --- limit parallel execution
-   🔁 Retry Mechanism --- exponential backoff with jitter
-   🛡️ Never Fails Globally --- allSettled-like behavior
-   📊 Priority Queue --- important tasks first (min-heap)
-   📈 Progress Tracking --- real-time updates
-   🔒 Order Preservation --- results match input order
-   📘 TypeScript Support --- ready-to-use typings
-   🧪 High Test Coverage --- 95%+ with Jest

------------------------------------------------------------------------

## 🚀 Getting Started

``` bash
git clone https://github.com/YOUR_USERNAME/promise-pool.git
cd promise-pool
npm install
```

------------------------------------------------------------------------

## 📖 Usage

``` js
import { PromisePool } from './src/index.js';

const pool = new PromisePool(5);
const tasks = urls.map(url => () => fetch(url).then(r => r.json()));
const results = await pool.run(tasks);
```

------------------------------------------------------------------------

## 🧪 Testing

-   25+ tests
-   95% coverage

------------------------------------------------------------------------

## 📄 License

MIT
