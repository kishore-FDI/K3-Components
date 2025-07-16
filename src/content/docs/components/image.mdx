---
title: Image Component (JSX)
description: Modern, accessible, and feature-rich React Image component with JS and TS support.
---

# Image Component

A robust `<Image />` React component with all modern features:

- **Fallback** for broken images
- **Accessibility** (alt, role, aria)
- **Lazy loading**
- **Responsive** (srcSet, sizes)
- **Blur-up placeholder**
- **Caching** (browser hints)
- **Customizable**

---

## JavaScript Version

```jsx
import React, { useState } from "react";

export function Image({
  src,
  alt,
  fallback,
  width,
  height,
  srcSet,
  sizes,
  className = "",
  style = {},
  loading = "lazy",
  placeholder,
  ...props
}) {
  const [imgSrc, setImgSrc] = useState(src);
  const [isLoaded, setIsLoaded] = useState(false);

  return (
    <span
      style={{ display: "inline-block", position: "relative", width, height }}>
      {placeholder && !isLoaded && (
        <img
          src={placeholder}
          alt=""
          aria-hidden="true"
          style={{
            position: "absolute",
            width: "100%",
            height: "100%",
            objectFit: "cover",
            filter: "blur(12px)",
            transition: "opacity 0.3s",
            opacity: isLoaded ? 0 : 1,
          }}
        />
      )}
      <img
        src={imgSrc}
        alt={alt}
        width={width}
        height={height}
        srcSet={srcSet}
        sizes={sizes}
        className={className}
        style={{
          ...style,
          display: "block",
          width: width || "100%",
          height: height || "auto",
          objectFit: "cover",
          transition: "opacity 0.3s",
          opacity: isLoaded ? 1 : 0,
        }}
        loading={loading}
        decoding="async"
        onLoad={() => setIsLoaded(true)}
        onError={() => setImgSrc(fallback || placeholder || "")}
        {...props}
      />
    </span>
  );
}
```

---

## TypeScript Version

```tsx
import React, { useState, ImgHTMLAttributes, CSSProperties } from "react";

export interface ImageProps extends ImgHTMLAttributes<HTMLImageElement> {
  src: string;
  alt: string;
  fallback?: string;
  width?: number | string;
  height?: number | string;
  srcSet?: string;
  sizes?: string;
  className?: string;
  style?: CSSProperties;
  loading?: "lazy" | "eager";
  placeholder?: string;
}

export function Image({
  src,
  alt,
  fallback,
  width,
  height,
  srcSet,
  sizes,
  className = "",
  style = {},
  loading = "lazy",
  placeholder,
  ...props
}: ImageProps) {
  const [imgSrc, setImgSrc] = useState(src);
  const [isLoaded, setIsLoaded] = useState(false);

  return (
    <span
      style={{ display: "inline-block", position: "relative", width, height }}>
      {placeholder && !isLoaded && (
        <img
          src={placeholder}
          alt=""
          aria-hidden="true"
          style={{
            position: "absolute",
            width: "100%",
            height: "100%",
            objectFit: "cover",
            filter: "blur(12px)",
            transition: "opacity 0.3s",
            opacity: isLoaded ? 0 : 1,
          }}
        />
      )}
      <img
        src={imgSrc}
        alt={alt}
        width={width}
        height={height}
        srcSet={srcSet}
        sizes={sizes}
        className={className}
        style={{
          ...style,
          display: "block",
          width: width || "100%",
          height: height || "auto",
          objectFit: "cover",
          transition: "opacity 0.3s",
          opacity: isLoaded ? 1 : 0,
        }}
        loading={loading}
        decoding="async"
        onLoad={() => setIsLoaded(true)}
        onError={() => setImgSrc(fallback || placeholder || "")}
        {...props}
      />
    </span>
  );
}
```

---

## Usage Example (JS)

```jsx
<Image
  src="/images/photo.jpg"
  alt="A beautiful landscape"
  width={600}
  height={400}
  fallback="/images/fallback.jpg"
  placeholder="/images/placeholder-blur.jpg"
  srcSet="/images/photo-600.jpg 600w, /images/photo-1200.jpg 1200w"
  sizes="(max-width: 600px) 100vw, 600px"
/>
```

## Usage Example (TS)

```tsx
<Image
  src="/images/photo.jpg"
  alt="A beautiful landscape"
  width={600}
  height={400}
  fallback="/images/fallback.jpg"
  placeholder="/images/placeholder-blur.jpg"
  srcSet="/images/photo-600.jpg 600w, /images/photo-1200.jpg 1200w"
  sizes="(max-width: 600px) 100vw, 600px"
/>
```

---

## WebP and Modern Image Formats

To serve modern formats like WebP, use the `srcSet` prop to provide multiple image sources. Browsers that support WebP will use it, while others will fall back to JPEG/PNG.

**Example:**

```jsx
<Image
  src="/images/photo.jpg"
  alt="A beautiful landscape"
  srcSet="/images/photo.webp 1x, /images/photo@2x.webp 2x, /images/photo.jpg 1x"
  sizes="(max-width: 600px) 100vw, 600px"
/>
```

- You can generate WebP images at build time using tools like [sharp](https://sharp.pixelplumbing.com/) or your build system.
- For automatic format selection, consider using a CDN or image optimization service that rewrites image URLs based on browser support.

---

## Caching

The React component cannot set HTTP cache headers; caching is controlled by your server or CDN. For best performance, configure your server to send strong cache headers for static images.

**Example HTTP header:**

```
Cache-Control: public, max-age=31536000, immutable
```

- This tells browsers and CDNs to cache the image for one year.
- If you use a CDN (like Vercel, Netlify, Cloudflare), enable long-term caching for your image assets.
- For dynamic images, consider using cache-busting techniques (e.g., unique URLs for each version).

---

## Accessibility

- Always provide descriptive `alt` text for accessibility.
- Use `role`, `aria-*`, and `tabIndex` as needed for your use case.
- The component supports all standard image accessibility features.

---

## Props

| Prop        | Type          | Required | Description                            |
| ----------- | ------------- | -------- | -------------------------------------- |
| src         | string        | Yes      | Image source URL                       |
| alt         | string        | Yes      | Alternative text for accessibility     |
| fallback    | string        | No       | Fallback image URL if main image fails |
| width       | number/string | No       | Width of the image (px, %, etc.)       |
| height      | number/string | No       | Height of the image (px, %, etc.)      |
| srcSet      | string        | No       | Responsive image sources               |
| sizes       | string        | No       | Responsive image sizes                 |
| className   | string        | No       | Additional CSS classes                 |
| style       | object        | No       | Inline styles                          |
| loading     | string        | No       | 'lazy' (default) or 'eager'            |
| placeholder | string        | No       | Low-res/blur image placeholder         |
| ...props    | any           | No       | Any other props (e.g., aria-_, data-_) |

---

## IndexedDB Caching (Advanced)

You can cache images in the browser using IndexedDB for offline or repeat access. This example uses the [idb-keyval](https://www.npmjs.com/package/idb-keyval) library for simplicity.

### 1. Install idb-keyval

```sh
npm install idb-keyval
```

---

### 2. JavaScript Version

```jsx
import React, { useState, useEffect } from "react";
import { get, set } from "idb-keyval";

export function Image({
  src,
  alt,
  fallback,
  width,
  height,
  srcSet,
  sizes,
  className = "",
  style = {},
  loading = "lazy",
  placeholder,
  cacheKey, // optional: custom cache key
  ...props
}) {
  const [imgSrc, setImgSrc] = useState(placeholder || src);
  const [isLoaded, setIsLoaded] = useState(false);

  useEffect(() => {
    let isMounted = true;
    const key = cacheKey || src;

    async function fetchAndCacheImage() {
      // Try to get from IndexedDB
      const cached = await get(key);
      if (cached && isMounted) {
        setImgSrc(cached);
        return;
      }
      // Fetch from network
      try {
        const response = await fetch(src, { cache: "force-cache" });
        const blob = await response.blob();
        const dataUrl = URL.createObjectURL(blob);
        if (isMounted) setImgSrc(dataUrl);
        // Store in IndexedDB as DataURL
        const reader = new FileReader();
        reader.onloadend = () => set(key, reader.result);
        reader.readAsDataURL(blob);
      } catch {
        if (isMounted) setImgSrc(fallback || src);
      }
    }

    fetchAndCacheImage();
    return () => {
      isMounted = false;
    };
  }, [src, cacheKey, fallback]);

  return (
    <span
      style={{ display: "inline-block", position: "relative", width, height }}>
      {placeholder && !isLoaded && (
        <img
          src={placeholder}
          alt=""
          aria-hidden="true"
          style={{
            position: "absolute",
            width: "100%",
            height: "100%",
            objectFit: "cover",
            filter: "blur(12px)",
            transition: "opacity 0.3s",
            opacity: isLoaded ? 0 : 1,
          }}
        />
      )}
      <img
        src={imgSrc}
        alt={alt}
        width={width}
        height={height}
        srcSet={srcSet}
        sizes={sizes}
        className={className}
        style={{
          ...style,
          display: "block",
          width: width || "100%",
          height: height || "auto",
          objectFit: "cover",
          transition: "opacity 0.3s",
          opacity: isLoaded ? 1 : 0,
        }}
        loading={loading}
        decoding="async"
        onLoad={() => setIsLoaded(true)}
        onError={() => setImgSrc(fallback || placeholder || src)}
        {...props}
      />
    </span>
  );
}
```

---

### 3. TypeScript Version

```tsx
import React, {
  useState,
  useEffect,
  ImgHTMLAttributes,
  CSSProperties,
} from "react";
import { get, set } from "idb-keyval";

export interface ImageProps extends ImgHTMLAttributes<HTMLImageElement> {
  src: string;
  alt: string;
  fallback?: string;
  width?: number | string;
  height?: number | string;
  srcSet?: string;
  sizes?: string;
  className?: string;
  style?: CSSProperties;
  loading?: "lazy" | "eager";
  placeholder?: string;
  cacheKey?: string;
}

export function Image({
  src,
  alt,
  fallback,
  width,
  height,
  srcSet,
  sizes,
  className = "",
  style = {},
  loading = "lazy",
  placeholder,
  cacheKey,
  ...props
}: ImageProps) {
  const [imgSrc, setImgSrc] = useState<string>(placeholder || src);
  const [isLoaded, setIsLoaded] = useState(false);

  useEffect(() => {
    let isMounted = true;
    const key = cacheKey || src;

    async function fetchAndCacheImage() {
      const cached = await get(key);
      if (cached && isMounted) {
        setImgSrc(cached as string);
        return;
      }
      try {
        const response = await fetch(src, { cache: "force-cache" });
        const blob = await response.blob();
        const dataUrl = URL.createObjectURL(blob);
        if (isMounted) setImgSrc(dataUrl);
        const reader = new FileReader();
        reader.onloadend = () => set(key, reader.result as string);
        reader.readAsDataURL(blob);
      } catch {
        if (isMounted) setImgSrc(fallback || src);
      }
    }

    fetchAndCacheImage();
    return () => {
      isMounted = false;
    };
  }, [src, cacheKey, fallback]);

  return (
    <span
      style={{ display: "inline-block", position: "relative", width, height }}>
      {placeholder && !isLoaded && (
        <img
          src={placeholder}
          alt=""
          aria-hidden="true"
          style={{
            position: "absolute",
            width: "100%",
            height: "100%",
            objectFit: "cover",
            filter: "blur(12px)",
            transition: "opacity 0.3s",
            opacity: isLoaded ? 0 : 1,
          }}
        />
      )}
      <img
        src={imgSrc}
        alt={alt}
        width={width}
        height={height}
        srcSet={srcSet}
        sizes={sizes}
        className={className}
        style={{
          ...style,
          display: "block",
          width: width || "100%",
          height: height || "auto",
          objectFit: "cover",
          transition: "opacity 0.3s",
          opacity: isLoaded ? 1 : 0,
        }}
        loading={loading}
        decoding="async"
        onLoad={() => setIsLoaded(true)}
        onError={() => setImgSrc(fallback || placeholder || src)}
        {...props}
      />
    </span>
  );
}
```

---

### Usage

```jsx
<Image
  src="/images/photo.jpg"
  alt="A beautiful landscape"
  cacheKey="photo-v1" // optional, for versioning
  // ...other props
/>
```

---

**Notes:**

- This approach stores images as Data URLs in IndexedDB.
- For large images or many images, consider browser quota limits.
- You can clear or version the cache by changing the `cacheKey`.
