
# 📦 react-smart-infinite

A powerful React NPM package that combines infinite scroll with toast notifications, spinners, skeleton loaders, and custom animations for a seamless user experience.

## 🚀 Features

### 🔁 Smart Infinite Scroll
- Auto-load when reaching the bottom
- Manual "Load More" trigger support
- Custom scroll thresholds
- Optimized with `IntersectionObserver`
- Supports horizontal scrolling

### 🔔 Toast Notifications
- Success, error, warning, and info types
- Customizable positions
- Auto-dismiss with animations
- Toast queue management

### ⏳ Loading Spinners & Skeleton Screens
- Multiple spinner styles (dots, bars, rings)
- Skeleton loaders with pulse/shimmer effects

### ✨ Animations
- Smooth scroll and lazy-load transitions
- Custom animation hooks

### ❗ Error & Retry Handling
- Automatic retries for failed loads
- Fallback UI and custom error messages

### 🧩 Additional Hooks & Components
- `usePageTracking` hook
- `useDebounce` hook
- `EmptyState`, `ToastProvider`, and `SmartInfiniteConfigProvider`

## 📦 Installation

```bash
npm install react-smart-infinite
```

Or with Yarn:

```bash
yarn add react-smart-infinite
```

## 🧠 Usage

### Wrap your App with Providers

```tsx
import {
  ToastProvider,
  SmartInfiniteConfigProvider
} from 'react-smart-infinite';

<SmartInfiniteConfigProvider config={{ scrollThreshold: 300 }}>
  <ToastProvider>
    <App />
  </ToastProvider>
</SmartInfiniteConfigProvider>
```

### Example: Infinite Scroll with Toasts

```tsx
import { InfiniteScroll, useToast, Spinner, Skeleton } from 'react-smart-infinite';

const Example = () => {
  const { addToast } = useToast();

  const fetchData = async () => {
    // Simulate API
    await new Promise(res => setTimeout(res, 1000));
    return Array.from({ length: 10 }, (_, i) => `Item ${i}`);
  };

  return (
    <InfiniteScroll
      fetchItems={fetchData}
      loader={<Spinner />}
      skeleton={<Skeleton />}
      onError={() => addToast({ type: 'error', message: 'Failed to load data' })}
    />
  );
};
```

## 📝 License

MIT License

Copyright (c) 2025 Jeswin John

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## 💡 Maintained By

Jeswin John  (Software Developer)
