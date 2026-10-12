# Using FrameKnife Metrics

FrameKnife Metrics draws a transparent canvas over the screen, always on top of other windows. This guide covers every part of it and a few workflows that put them together.

- [The overlay](#the-overlay)
- [The wheel](#the-wheel)
- [Elements](#elements)
- [The pen](#the-pen)
- [Units, scale and calculator](#units-scale-and-calculator)
- [Grid, rulers and guides](#grid-rulers-and-guides)
- [Canvas and aspect ratios](#canvas-and-aspect-ratios)
- [Layouts and slots](#layouts-and-slots)
- [Settings and themes](#settings-and-themes)
- [Sound](#sound)
- [Shortcuts](#shortcuts)
- [Workflows](#workflows)
- [Files](#files)
- [Troubleshooting](#troubleshooting)

## The overlay

FrameKnife Metrics opens as an overlay over the screen it is on, leaving a fixed taskbar uncovered and an auto-hide taskbar reachable. Clicks on empty areas pass through to the windows below. Only these take the mouse:

- the rulers along the top and left edges,
- guides,
- element anchors,
- the grip in the top-left corner,
- the whole canvas while the pen is out.

**Edit › Lock** (Shift+L) hands even those to the app below: clicks pass through elements, guides and rulers, and the anchors hide. The corner grip and Ctrl + right-click still open the wheel. The lock is saved with the layout, so a spec loads locked; creating an element or taking up the pen unlocks.

Measurements are in physical screen pixels, so Windows display scaling does not change them. The Measure group switches them to grid points, meters or centimeters.

**F11** switches between the overlay and a see-through window with a frame, which can be moved to another monitor. Press F11 again there to cover that monitor. **Quit** (Ctrl+Q) or closing the window ends FrameKnife Metrics completely.

## The wheel

Hold **Ctrl** and **right-click** anywhere on the canvas, or hold a click on the corner grip. The wheel opens at the cursor; move toward a group and rest on it to open its items in the outer ring, then release over an item to run it. Shortcuts are shown next to their items.

| Group | Items |
| --- | --- |
| Create | Line, Box, Cross, Mirror, Compass, Text, Pen |
| Edit | Undo, Redo, Delete, Duplicate, Snap All, Lock, Clear Ink, Clear |
| Canvas | Screen, 4:3, 16:9, 19.5:9, 20:9, 21:9, 32:9, your saved ratios, Custom, Ratios |
| Grid | Grid, Snap Elements, Ruler, Settings |
| Guides | Cursor Guides, Snap, Delete Selected, Clear All, Settings |
| Measure | Pixels, Grid Points, Meters, Centimeters, Scale, Calculator |
| Layouts | the Layouts window |
| View | Appearance, Metrics, Sounds, Shortcuts, Window Mode, Help, Quit |

## Elements

New elements appear at the center of the canvas. Drag their anchors to place them; the measurement updates as you drag, and a level line follows the anchor across the canvas.

| Element | Anchors | Shows | Typical use |
| --- | --- | --- | --- |
| Line | both ends, middle | `L` length | distances, heights, paddings |
| Box | four corners, center | `W` width and `H` height | targets, crops, safe areas, cards |
| Cross | four arm ends, center | `A` and `B` arm lengths and the angle | angles, horizons, diagonals, perspective rays |
| Mirror | center, two points and their mirrored twins | `D` distance between a point and its twin | symmetry around a point |
| Compass | pivot, two arm ends | `R` radius, the angle between the arms, `Area` of the circle | angles, round objects, arcs |
| Text | its position | your text | labels on a layout |

The middle and center anchors move a whole element. Every element is numbered so you can tell them apart in a busy layout. Double-click a text anchor to edit its text. **Delete** removes the selected element. Hold **Ctrl** and drag any anchor to carry off a copy of its element, or press **Ctrl+D** for a copy of the selected one, one grid cell over.

A mirror reflects its two points through its center. To check left and right sides, put the center on the axis at the height of the points you compare; both twins then land on the other side at the same height.

A compass sweeps a circle with its first arm and opens an angle with the second. Put the pivot on a vertex to read the angle between two edges, or on the center of something round to read its radius and area. Dragging the pivot carries both arms.

## The pen

**Create › Pen** or **Shift+P** takes up the pen, and the cursor turns into a nib. While the pen is out the canvas takes the mouse: hold the left button to write, release to lift the pen. **Esc** or Shift+P again puts it away, and clicks pass through again.

With a pen (a Surface Pen, a Wacom or any Windows Ink pen) the line follows how hard you press, from a quarter of the line on a light touch to all of it on a full press, and the eraser end wipes every stroke it touches. Each sweep of the eraser is one step to undo.

The line is fine, swells a little when it runs across the oblique nib, leaves a small drop where the pen touches down and thins out where it lifts. Each stroke is saved with the layout. **Ctrl+Z** takes back the last stroke; **Edit › Clear Ink** wipes every stroke and keeps the measurements.

## Units, scale and calculator

Each layout reads its measurements in one unit, chosen in the **Measure** group: element readings, guide labels, ruler numbers and the cursor readout all follow it. **View › Metrics** (Shift+R) hides the measurements, element numbers and guide positions for a clean view, and shows them again.

- **Pixels** are physical screen pixels.
- **Grid Points** count grid cells: one point is one cell along each axis, so a line across three cells reads `L 3 pt`.
- **Meters** and **Centimeters** need the size of a pixel. **Measure › Scale** takes it typed in (`1 px is 0.75 cm`) or from a line you know: select a line along a 2.10 m door, open Scale and type 2.10 m.

**Measure › Calculator** (Shift+C) stays open beside the canvas. It lists every reading on the canvas; click one to drop its value into the sum. Type with the keyboard or the keypad (`+ − × ÷ ^ %`, parentheses, a dot or a comma for decimals), press Enter for the result, and pick earlier results from the history. **Place on canvas** writes the sum and its result as a text element.

## Grid, rulers and guides

The grid divides the canvas into whole cells close to the spacing you set, so the lines land on both edges and every cell is the same size. Settings › Grid sets the spacing, the line thickness and the opacity, and shows the exact cell size it produced.

- **Grid › Snap Elements** makes anchors snap to grid lines. **Edit › Snap All** snaps everything already on the canvas.
- **Click a ruler** to add a guide, then drag it into place. Click a guide to select it, drag to move it.
- **Guides › Snap** snaps ruler guides to the grid, separately from elements.
- **Shift + mouse wheel** over the canvas sizes the grid while it shows: each notch away from you widens the cells by a tenth, each notch back narrows them, down to the finest grid that stays smooth. That turn never reaches the app below, and Shift + click still does.
- A very fine grid draws thousands of lines on every redraw. When the spacing drops below the finest one that stays smooth on your canvas, FrameKnife Metrics asks first: keep it, stop warning, or lock the grid at the safe spacing. Settings › Grid turns the lock and the warning back off or on.
- **Guides › Cursor Guides** shows lines through the cursor with its position in the current unit and as a fraction of the canvas.
- Settings › Guides sets how strong and how thick ruler guides are drawn. A guide shows the theme's stroke color only while you place or move it.

## Canvas and aspect ratios

**Canvas › Screen** covers the whole screen. The presets fit a frame of that ratio inside it, centered: 4:3, 16:9, 19.5:9, 20:9, 21:9 and 32:9. **Ratios** saves aspect ratios of your own, like 4:5 for a portrait post or 2.39:1 for a scope frame: type the two sides, Save and use, and up to six of them join the presets on the wheel. **Custom** takes an exact size in pixels. Elements and guides keep their place relative to the canvas when it changes.

## Layouts and slots

A layout is everything on the canvas: elements, ink, guides, grid, canvas and guide settings, and its unit and scale.

- A first start opens a demo layout in slot 1: a golden ratio construction, the rectangle split into squares with a compass turning in each, the cut marked with ruler guides, a label as text and 1.618 written with the pen, with its metrics hidden. Press **Shift+R** to read it, or delete it in the Layouts window.
- **Layouts** (Ctrl+O) opens the library: load, save, duplicate, rename, delete, import and export.
- **Ctrl+S** saves over the loaded layout; a layout never saved opens the Layouts window instead.
- **Ctrl+1 to Ctrl+9** load the first nine layouts from anywhere, even while another app has the focus. Pressing the number of the layout already on screen minimizes FrameKnife Metrics, which rests until the next press brings it back; if the layout was edited since, the press loads the saved one instead (Ctrl+Z brings the edits back). A slot with no layout opens a blank one. Settings › Shortcuts can limit these keys to the app's own window.

## Settings and themes

**View › Appearance** opens Settings. Every change shows at once.

- **Appearance:** the theme, the wheel (or the theme's own), the wheel size, how elements are colored (by the theme, a new random color for each element, or one custom color), and the sound effects with their volume.
- **Grid:** spacing, thickness and opacity, the lock that keeps the grid light and the warning before it gets heavy.
- **Guides:** cursor guides, guide snap, opacity, thickness and color, and whether the metrics show and at what opacity.
- **Shortcuts:** every command can be given its own keys.

| Theme | Strokes | Anchors | Palette | Wheel |
| --- | --- | --- | --- | --- |
| Laser | thin beams with a hot core | glowing dots | Gothic Blood | Crypt |
| Tracery | translucent stained glass | hollow quatrefoils | Cathedral | Glass |
| Blades | tapered steel | knives and saw rings | Forge | Saw |
| Square | ticked tape | small squares | Blueprint | Frame |
| Circle | halftone print | registration targets | Press | Iris |
| Diamond | survey line with chain ticks | stakes | Field | Dial |

## Sound

FrameKnife Metrics plays short effects as you work: a detent as the wheel opens and its items pass under the pointer, the theme's own accent when an item runs, a click on anchors, a tick for every grid step while snapping, a nib on paper when the pen touches down, a frame locking into place when the canvas changes and a sweep when a layout loads. Settings › Appearance has the volume and an on/off switch; **View › Sounds** or **Ctrl+M** mutes and restores them.

## Shortcuts

| Keys | Command |
| --- | --- |
| Shift+1 / 2 / 3 / 4 / 5 | Line / Box / Cross / Mirror / Compass |
| Shift+T | Text |
| Shift+P | Pen; Esc puts it away |
| Shift+L | Lock or unlock the canvas |
| Ctrl+Z / Ctrl+Y | Undo / Redo |
| Delete | Delete the selected element or guide |
| Ctrl+S | Save the layout |
| Ctrl+O | Layouts window |
| Shift+C | Calculator |
| Shift+R | Show or hide the metrics |
| Ctrl+D | Duplicate the selected element |
| Ctrl+1 … Ctrl+9 | Load a layout slot, or a blank layout from an empty one |
| Shift + mouse wheel | Grid coarser or finer |
| F11 | Overlay or window mode |
| Ctrl+M | Mute or restore the sound effects |
| Ctrl+Q | Quit |

Keys other than the layout slots reach FrameKnife Metrics while it has the focus, for example right after you open the wheel or drag an anchor.

## Workflows

### Match a website to its design

1. Over the design (a mockup, an image or the designer's build), place boxes on the key blocks and guides on the column edges.
2. Save the layout, say as "Dashboard spec", in slot 1.
3. Open the site you are building and press **Ctrl+1**.
4. Anything off shows against the frames: a card 12 px out of its column, a 36 px button that should be 48 px. Fix the CSS until the page sits in the frames.

### Set up perspective and symmetry before sketching

1. Pull a guide from the left ruler for the horizon.
2. Create a cross and drag its center to the vanishing point; drag one arm end to set the angle of the rays, and the other to set their reach.
3. Create a mirror, put its center on the axis of the subject, and its points on one side: their twins show where the other side must go.
4. Sketch in your painting app; the overlay stays on top while you draw.

### Measure from a photo

1. Find something in the photo whose real size you know, in the same plane as what you want to measure: a door, a sheet of paper, a tile.
2. Draw a line along it and keep it selected, say `L 280 px` for a 2.10 m door.
3. Open **Measure › Scale** and type 2.10 m. Every reading now shows meters: a wall line reads `L 6.00 m`, and a compass over a round table reads its radius and its area in m².
4. For anything else, open the calculator: click the readings to drop them in, and place the result on the canvas.
5. Write notes next to the lines with the pen.

### Check a game HUD across aspect ratios

1. Create a mirror with its center at the middle of the screen, at the height of the lower panels, and its points on the outer and inner corners of the right panel. The twins land where the left panel's corners should be.
2. Switch Canvas to 21:9 and 32:9 to see what a cinematic or ultrawide crop keeps.

### Frame a vertical crop for video

1. Draw a box the height of the viewer with a 9:16 width (W 405 px for a 720 px viewer).
2. Draw a second box for the title safe area, then save both as a layout for the next edit.

## Files

| File | Holds |
| --- | --- |
| `%USERPROFILE%\.frameknife\library.json` | Saved layouts |
| `%USERPROFILE%\.frameknife\preferences.json` | Settings and shortcuts |

To remove FrameKnife Metrics, delete `FrameKnifeMetrics.exe` and the `.frameknife` folder.

## Troubleshooting

**Windows shows "Windows protected your PC".** FrameKnife Metrics is a new app without a code-signing certificate. Choose **More info › Run anyway**.

**The wheel does not open.** Make sure the cursor is over the canvas and hold Ctrl before the right-click. If another always-on-top window is open, pressing Ctrl over the canvas brings FrameKnife Metrics back on top.

**Nothing draws over my game.** Games in exclusive fullscreen do not allow other windows on top. Switch the game to borderless or windowed mode.

**Ctrl+1 opens a blank layout.** The slot is empty until a layout is saved in that position in the Layouts window; empty slots answer only while FrameKnife Metrics has the focus. If another app already uses the same keys system-wide, change them in Settings › Shortcuts.
