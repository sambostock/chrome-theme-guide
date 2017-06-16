# Google Chrome Theme Guide

## Introduction

I wanted to make a simple Chrome Theme. The docs sucked, so I decided to make my own.

## Overview

_Themes_ are basically just _Extensions_ which don't package in any HTML or JavaScript. All you need is a directory with a `manifest.json` file (describing the theme), and an optional `/images` subdirectory. The whole thing gets packaged up as a glorified _ZIP_ file.

## Boilerplate

There are a couple values which need to be included in `manifest.json`:

```javascript
{
  "manifest_version": 2, // Manifest format version
  "version": "0.1", // Theme version
  
  "name": "My Awesome Theme"
  "description": "An awesome theme, for awesome people",
  
  // ...
}
```

## Colors

Colors for various portions of the UI are described under the `colors` property:

```javascript
{
  // ...
  "colors": {
    "frame_incognito_inactive": [0, 123, 255]
  }
  // ...
}
```

Property | Source ID Constant
--- | ---
`frame` | `ThemeProperties::COLOR_FRAME`
`frame_inactive` | `ThemeProperties::COLOR_FRAME_INACTIVE`
`frame_incognito` | `ThemeProperties::COLOR_FRAME_INCOGNITO`
`frame_incognito_inactive` | `ThemeProperties::COLOR_FRAME_INCOGNITO_INACTIVE`
`toolbar` | `ThemeProperties::COLOR_TOOLBAR`
`tab_text` | `ThemeProperties::COLOR_TAB_TEXT`
`tab_background_text` | `ThemeProperties::COLOR_BACKGROUND_TAB_TEXT`
`bookmark_text` | `ThemeProperties::COLOR_BOOKMARK_TEXT`
`ntp_background` | `ThemeProperties::COLOR_NTP_BACKGROUND`
`ntp_text` | `ThemeProperties::COLOR_NTP_TEXT`
`ntp_link` | `ThemeProperties::COLOR_NTP_LINK`
`ntp_header` | `ThemeProperties::COLOR_NTP_HEADER`
`button_background` | `ThemeProperties::COLOR_BUTTON_BACKGROUND`

## Images

Images can be used for certain portions of the UI. Their paths can be specified under the `images` property:

```javascript
{
  // ...
  "images": {
    "theme_frame" : "images/theme_frame.png",
  }
  // ...
}
```

Property | Source ID Constants | Notes
--- | --- | ---
`theme_frame` | `PRS_THEME_FRAME`, `IDR_THEME_FRAME` |
`theme_frame_inactive` | `PRS_THEME_FRAME_INACTIVE`, `IDR_THEME_FRAME_INACTIVE` |
`theme_frame_incognito` | `PRS_THEME_FRAME_INCOGNITO`, `IDR_THEME_FRAME_INCOGNITO` |
`theme_frame_incognito_inactive` | `PRS_THEME_FRAME_INCOGNITO_INACTIVE`, `IDR_THEME_FRAME_INCOGNITO_INACTIVE` |
`theme_toolbar` | `PRS_THEME_TOOLBAR`, `IDR_THEME_TOOLBAR` |
`theme_tab_background` | `PRS_THEME_TAB_BACKGROUND`, `IDR_THEME_TAB_BACKGROUND` |
`theme_tab_background_incognito` | `PRS_THEME_TAB_BACKGROUND_INCOGNITO`, `IDR_THEME_TAB_BACKGROUND_INCOGNITO` | Unsupported on macOS
`theme_tab_background_v` | `PRS_THEME_TAB_BACKGROUND_V`, `IDR_THEME_TAB_BACKGROUND_V` |
`theme_ntp_background` | `PRS_THEME_NTP_BACKGROUND`, `IDR_THEME_NTP_BACKGROUND` |
`theme_frame_overlay` | `PRS_THEME_FRAME_OVERLAY`, `IDR_THEME_FRAME_OVERLAY` |
`theme_frame_overlay_inactive` | `PRS_THEME_FRAME_OVERLAY_INACTIVE`, `IDR_THEME_FRAME_OVERLAY_INACTIVE` |
`theme_button_background` | `PRS_THEME_BUTTON_BACKGROUND`, `IDR_THEME_BUTTON_BACKGROUND` |
`theme_ntp_attribution` | `PRS_THEME_NTP_ATTRIBUTION`, `IDR_THEME_NTP_ATTRIBUTION` |
`theme_window_control_background` | `PRS_THEME_WINDOW_CONTROL_BACKGROUND`, `IDR_THEME_WINDOW_CONTROL_BACKGROUND` |

## Properties

Some UI elements accept additional properties, specified under the `properties` property:

```javascript
{
  // ...
  "properties": {
    "ntp_background_repeat": true
  }
  // ...
}
```

Property | Source ID Constant
--- | ---
`ntp_background_alignment` | `ThemeProperties::NTP_BACKGROUND_ALIGNMENT`
`ntp_background_repeat` | `ThemeProperties::NTP_BACKGROUND_TILING`
`ntp_logo_alternate` | `ThemeProperties::NTP_LOGO_ALTERNATE`

## Tints

Tints can be applied to some UI elements, and are specified under the `tints` property, in _Hue-Saturation-Lightness_ format:

```javascript
{
  // ...
  "tints": {
    "frame_incognito_inactive": [0, 0.5, 0.5]
  }
  // ...
}
```

Property | Source ID Constant
--- | ---
`buttons` | `ThemeProperties::TINT_BUTTONS`
`frame` | `ThemeProperties::TINT_FRAME`
`frame_inactive` | `ThemeProperties::TINT_FRAME_INACTIVE`
`frame_incognito` | `ThemeProperties::TINT_FRAME_INCOGNITO`
`frame_incognito_inactive` | `ThemeProperties::TINT_FRAME_INCOGNITO_INACTIVE`
`background_tab` | `ThemeProperties::TINT_BACKGROUND_TAB`
