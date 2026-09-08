# Terrain rendering contract

These are the non-negotiable visual rules for high-ground terrain. Keep this document in sync with any future terrain-rendering changes.

## What the terrain means

- The board is still a fixed logical grid. Players select individual cells.
- Orthogonally adjacent high-ground cells form one connected visual component.
- A connected component is a gameplay grouping, not a license to paint a large rectangle over the board.

## Required appearance

- Terrain artwork has transparent margins.
- The underlying cell background must remain visible through those transparent margins: red for Player 2 territory, blue for Player 1 territory, and neutral blue-gray in the middle.
- High-ground cells must not replace the underlying zone color with white, cream, or the board background.
- Adjacent high-ground cells must merge visually. There must be no visible horizontal or vertical seam between them.
- Only the outside perimeter of a component may show its raised/dirt edge.
- Disconnected components must remain visually separate.

## Forbidden approaches

- Do not add an opaque background to `.cell.high-ground`.
- Do not stretch `high-ground-1111.png` to a component's bounding box; that creates rectangular splotches and hides the zone colors. A fixed-scale continuous meadow texture may be clipped to the component outline.
- Do not add broad solid-color seam bars. A seam treatment must be narrow, texture-compatible, and fade into the terrain on both sides.
- Do not render independent borders on shared edges.
- Do not allow white or pale rectangles to appear around transparent terrain artwork.

## Implementation guidance

- Clip one fixed-scale meadow texture to the full connected-component outline so internal cells share one continuous green surface.
- Use the supplied neighbor-aware sprites only as a narrow perimeter edge layer. The edge must come from the irregular transparent dirt/grass artwork, not from synthetic rectangular or multi-line SVG strokes.
- Exposed sides may use rotated crops of the supplied downhill earth artwork so the visible slope is brown soil/rock on every direction, including top and side edges.
- Keep the outside of the outline transparent so red, blue, and neutral cell colors remain visible beyond the slope.
- Concave L-joints are formed by the rounded component outline and the sprite edges; do not add a broad corner patch, rectangular band, or terrain splotch over the adjacent zone cell.
- Every exposed corner, including concave interior corners, follows a circular/filleted outline. A small rotated source corner sprite may bridge the inside turn, but it must stay narrow so the red/blue zone behind it remains visible.
- Keep the terrain layer below pieces but visible through transparent high-ground cells.
- If the terrain layer is below the cells, provide the zone-color backing inside the terrain layer for high-ground cells; otherwise the cell background will cover the artwork.
- Test isolated tiles, horizontal pairs, vertical pairs, 2×2 blocks, L-shapes, disconnected components, and terrain placed in both red and blue zones.
