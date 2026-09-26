# Remotion implementation

Use this when the runtime is Claude Code + Remotion.

## Project shape

```
src/
  Root.tsx
  Composition.tsx          # timeline only
  theme.ts                 # 3 colors, type, easing, fps
  scenes/
    Hook.tsx
    FeatureA.tsx
    FeatureB.tsx
    Resolve.tsx
  components/
    ProductFrame.tsx
    DisplayType.tsx
```

`theme.ts` is the brand constitution. Scenes may not invent colors.

## Timing

- Drive everything with `useCurrentFrame()` + `interpolate` / `spring`
- No `useEffect` timers, no CSS random transitions as the source of truth
- Default `fps = 30`. Name frame ranges in comments to match the shot list
- Springs — high damping, low mass. Premium = settles, does not wobble

## Visual defaults

- Canvas 1920x1080 (or 1080x1920 if the brief is vertical)
- Background from theme void (`#000` / `#0A0A0A` / `#F5F5F7`)
- Inter / SF-like sans, 2 weights max, letter-spacing +0.02 to +0.04em on display
- Safe type — no line wider than ~20ch on 1080p
- Captions as a separate layer, not baked into the hero type

## Scene contract

Each scene component receives `{frame, start, duration}` or uses `<Sequence>`.
Each scene still-frame at its mid-hold must look like a poster.

## Export

- ProRes or high-bitrate H.264 for master
- Also a 1080 captioned cut
- Do not add progress bars or player chrome
