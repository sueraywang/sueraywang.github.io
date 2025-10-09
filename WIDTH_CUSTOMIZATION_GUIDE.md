# 📐 Content Width Customization Guide

## Changes Made

### 1. Created Custom CSS: `assets/css/custom.css`

**Width Settings:**
- **Standard screens (1200px+)**: Container max-width = 1400px
- **Large screens (1600px+)**: Container max-width = 1600px  
- **Article content**: max-width = 1200px
- **Project pages**: max-width = 1300px
- **Mobile screens**: Maintains 95% width with proper margins

### 2. Updated Configuration: `config/_default/params.yaml`

Added custom CSS plugin configuration:
```yaml
plugins_css: ["custom"]
```

This tells HugoBlox to load `assets/css/custom.css`

---

## 🎨 What Changed Visually

### Before:
- Narrow content with wide white margins
- Default Bootstrap container (~1140px max)
- Lots of unused screen space

### After:
- Wider content area (up to 1400-1600px)
- Better use of screen real estate
- Reduced side margins
- Still maintains readability
- Responsive on mobile devices

---

## 🔧 Customization Options

### To Make Content Even Wider:

Edit `assets/css/custom.css` and adjust these values:

```css
/* Change from 1400px to your preferred width */
.container {
  max-width: 1400px !important;  /* Change this number */
}

.article-container {
  max-width: 1200px !important;  /* Change this number */
}
```

### To Make Content Narrower:

Reduce the max-width values:
```css
.container {
  max-width: 1200px !important;  /* Narrower */
}
```

### To Keep Different Widths for Different Sections:

The CSS already supports this:
- **General pages**: Controlled by `.container`
- **Articles/Posts**: Controlled by `.article-container`  
- **Projects**: Controlled by `.project-detail`
- **Home sections**: Controlled by `.home-section`

---

## 📱 Responsive Breakpoints

The custom CSS includes responsive design:

| Screen Size | Container Width |
|-------------|----------------|
| < 768px (Mobile) | 95% width |
| 768px - 1200px (Tablet) | Default Bootstrap |
| 1200px - 1600px (Desktop) | 1400px max |
| > 1600px (Large Desktop) | 1600px max |

---

## 🎯 What Each CSS Class Controls

```css
.container              → Main site container (all pages)
.article-container      → Blog posts and article pages
.project-detail         → Individual project pages
.universal-wrapper      → Overall page wrapper
.home-section           → Homepage sections
.page-body              → General page content
```

---

## 🧪 Testing Checklist

After deployment, test these pages:

- [ ] **Homepage** - Check section widths
- [ ] **Project pages** - Check content width
- [ ] **Publications** - Check list layout
- [ ] **About page** - Check text width
- [ ] **Mobile view** - Should still look good
- [ ] **Tablet view** - Should be responsive

---

## 🚀 Deploy These Changes

```bash
# Stage the new files
git add assets/css/custom.css
git add config/_default/params.yaml

# Commit with descriptive message
git commit -m "Add custom CSS for wider content layout"

# Push to deploy
git push origin main
```

Wait 2-3 minutes, then visit your site to see the changes!

---

## 🔄 How to Revert Width Changes

### Option 1: Remove Custom CSS (Back to Default)
```bash
# Remove the custom CSS reference
git rm assets/css/custom.css

# Edit params.yaml to remove the plugins_css line
# Then commit and push
```

### Option 2: Adjust Width Values
Just edit the pixel values in `assets/css/custom.css` and push.

---

## 💡 Pro Tips

### 1. **Optimal Reading Width**
Research shows optimal line length for reading is 50-75 characters. The current settings maintain this by:
- Using wider containers for layout
- But keeping article text at reasonable width (1200px)

### 2. **Different Widths for Different Content**
You can set different widths:
```css
/* Wide for image galleries */
.project-detail {
  max-width: 1600px !important;
}

/* Narrower for text-heavy content */
.article-container {
  max-width: 900px !important;
}
```

### 3. **Test on Multiple Devices**
Use browser dev tools (F12) to test responsive design:
- Toggle device toolbar
- Test iPhone, iPad, Desktop sizes

---

## 📊 Quick Reference: Common Widths

| Purpose | Recommended Max-Width |
|---------|----------------------|
| Text articles | 800-1000px |
| Mixed content | 1200px |
| Image galleries | 1400-1600px |
| Full-width layouts | 1800px+ |

---

## 🎨 Color Coding in CSS

The custom CSS also includes:
- ✨ **Hover effects** on collapsible sections
- 🎯 **Better spacing** for details/summary elements
- 📱 **Responsive padding** that adapts to screen size
- 📊 **Full-width tables** for better data display

---

**Created**: October 9, 2025  
**Purpose**: Reduce side margins and better utilize screen space  
**Theme**: HugoBlox (Hugo Academic)  
**Status**: Ready to deploy
