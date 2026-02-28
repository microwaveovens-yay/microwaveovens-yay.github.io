# Mazel GitHub Pages – Universal Links

Landing page and Apple App Site Association (AASA) host for the [Mazel](https://apps.apple.com/app/id6740949566) iOS app.

Served at `https://microwaveovens-yay.github.io`

## URL structure

| Universal Link | Opens in Mazel |
|---|---|
| `https://microwaveovens-yay.github.io/story/story_025` | Stories tab → story modal |
| `https://microwaveovens-yay.github.io/saying/saying_001` | Library tab → saying highlight |
| `https://microwaveovens-yay.github.io/sefirah` | Profile tab |
| `https://microwaveovens-yay.github.io/` | App home |

## How it works

1. **App installed**: iOS intercepts `https://microwaveovens-yay.github.io/story/*` links before Safari opens them, and routes directly into the Mazel app via the `linking` config in `AppNavigator.tsx`.
2. **App not installed**: Page loads, tries `mazel://` custom scheme via hidden iframe, detects failure after 2.5s, redirects to App Store.

## Verify AASA is live

```bash
curl -s https://microwaveovens-yay.github.io/.well-known/apple-app-site-association | python3 -m json.tool
```
