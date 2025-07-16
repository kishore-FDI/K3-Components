---
title: Image Component
description: A modern, accessible, and feature-rich React Image component for your component library.
---

A robust `<Image />` React component with all modern features:

- **Fallback** for broken images
- **Accessibility** (alt, role, aria)
- **Lazy loading**
- **Responsive** (srcSet, sizes)
- **Blur-up placeholder**
- **Caching** (browser hints)
- **Customizable**

---

## Usage Example

<div style="position: relative;">
  <button id="copy-btn" style="position: absolute; right: 0.5rem; top: 0.5rem; z-index: 2; padding: 0.3em 0.8em; border-radius: 4px; border: none; background: #222; color: #fff; cursor: pointer; font-size: 0.9em;">Copy</button>
</div>

```jsx {1} id="image-component-code"
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

<script>
const btn = document.getElementById('copy-btn');
if (btn) {
  btn.onclick = function() {
    const code = document.querySelector('[id="image-component-code"]');
    if (code) {
      navigator.clipboard.writeText(code.innerText);
      btn.innerText = 'Copied!';
      setTimeout(() => (btn.innerText = 'Copy'), 1200);
    }
  };
}
</script>

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

## Features

- **Fallback**: Shows a fallback image if the main image fails to load.
- **Accessibility**: Requires `alt` text, supports all ARIA attributes.
- **Lazy Loading**: Uses `loading="lazy"` by default.
- **Responsive**: Supports `srcSet` and `sizes` for responsive images.
- **Blur-up Placeholder**: Shows a blurred placeholder until the main image loads.
- **Caching**: Uses browser defaults; for advanced caching, serve images with proper HTTP headers.
- **Customizable**: Pass any extra props (e.g., `role`, `aria-*`, `data-*`).

---

## Example Usage

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

---

## Tips

- Always provide descriptive `alt` text for accessibility.
- Use `srcSet` and `sizes` for responsive images.
- Use a small, blurred placeholder for better UX on slow connections.
- For best caching, configure your server to send proper cache headers for images.

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
