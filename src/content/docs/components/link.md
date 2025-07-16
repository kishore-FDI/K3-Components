---
title: Link Component (JSX)
description: Modern, accessible, and feature-rich React Link component with JS and TS support.
---

# Link Component

A robust `<Link />` React component with all modern features:

- **External/internal link handling**
- **Accessibility** (aria, rel, role, tabIndex)
- **Security** (noopener, noreferrer)
- **Prefetching** (optional)
- **Customizable** (className, style)
- **Supports buttons-as-links**
- **Active state**

---

## JavaScript Version

```jsx
import React from "react";

export function Link({
  href,
  children,
  external,
  prefetch,
  className = "",
  style = {},
  activeClassName = "active",
  isActive,
  ...props
}) {
  const isExternal =
    typeof external === "boolean"
      ? external
      : href && /^(https?:)?\/\//.test(href);

  // Optionally add prefetch logic here (e.g., IntersectionObserver)

  // Optionally handle active state
  const active = typeof isActive === "boolean" ? isActive : false;

  return (
    <a
      href={href}
      className={className + (active ? ` ${activeClassName}` : "")}
      style={style}
      target={isExternal ? "_blank" : undefined}
      rel={isExternal ? "noopener noreferrer" : undefined}
      aria-current={active ? "page" : undefined}
      {...props}>
      {children}
    </a>
  );
}
```

---

## TypeScript Version

```tsx
import React, { AnchorHTMLAttributes, ReactNode, CSSProperties } from "react";

export interface LinkProps extends AnchorHTMLAttributes<HTMLAnchorElement> {
  href: string;
  children: ReactNode;
  external?: boolean;
  prefetch?: boolean;
  className?: string;
  style?: CSSProperties;
  activeClassName?: string;
  isActive?: boolean;
}

export function Link({
  href,
  children,
  external,
  prefetch,
  className = "",
  style = {},
  activeClassName = "active",
  isActive,
  ...props
}: LinkProps) {
  const isExternal =
    typeof external === "boolean"
      ? external
      : href && /^(https?:)?\/\//.test(href);

  // Optionally add prefetch logic here (e.g., IntersectionObserver)

  // Optionally handle active state
  const active = typeof isActive === "boolean" ? isActive : false;

  return (
    <a
      href={href}
      className={className + (active ? ` ${activeClassName}` : "")}
      style={style}
      target={isExternal ? "_blank" : undefined}
      rel={isExternal ? "noopener noreferrer" : undefined}
      aria-current={active ? "page" : undefined}
      {...props}>
      {children}
    </a>
  );
}
```

---

## Usage Example (JS)

```jsx
<Link href="/about">About Us</Link>
<Link href="https://example.com" external>External Site</Link>
<Link href="/contact" className="nav-link" isActive>Contact</Link>
```

## Usage Example (TS)

```tsx
<Link href="/about">About Us</Link>
<Link href="https://example.com" external>External Site</Link>
<Link href="/contact" className="nav-link" isActive>Contact</Link>
```

---

## Prefetching (Advanced)

To prefetch linked pages for faster navigation, you can add a `prefetch` prop and implement logic using `IntersectionObserver` or a router's prefetch API.

**Example (pseudo-code):**

```jsx
// Inside the Link component
React.useEffect(() => {
  if (prefetch && href && !isExternal) {
    // Prefetch logic here (e.g., fetch or router.prefetch)
  }
}, [prefetch, href, isExternal]);
```

---

## Accessibility

- Always provide descriptive link text for accessibility.
- Use `aria-current="page"` for the current/active page.
- External links automatically get `rel="noopener noreferrer"` and `target="_blank"` for security.
- Supports all standard anchor accessibility features.

---

## Props

| Prop            | Type      | Required | Description                            |
| --------------- | --------- | -------- | -------------------------------------- |
| href            | string    | Yes      | Link destination URL                   |
| children        | ReactNode | Yes      | Link content                           |
| external        | boolean   | No       | Force external link behavior           |
| prefetch        | boolean   | No       | Prefetch target page (advanced)        |
| className       | string    | No       | Additional CSS classes                 |
| style           | object    | No       | Inline styles                          |
| activeClassName | string    | No       | CSS class for active state             |
| isActive        | boolean   | No       | Mark link as active                    |
| ...props        | any       | No       | Any other props (e.g., aria-_, data-_) |

---

## Security

- External links use `rel="noopener noreferrer"` and `target="_blank"` to prevent tab-napping and improve security.
- Always validate URLs if accepting user input.

---

## SEO

- Use semantic, descriptive link text.
- Avoid using only "click here" or "read more" as link text.
- Use proper heading and navigation structure for best results.

---

## Notes

- You can extend this component to support router integration (e.g., React Router, Next.js Link) by swapping the `<a>` for a router link component.
- For button-like links, add `role="button"` and keyboard handlers as needed.
