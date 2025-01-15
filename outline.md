# User Interface

## Toolbox

The toolbox contains a selection of editing tools like the paintbrush,
color picker, selection tools, etc.

## Toolbar

The toolbar contains shortcuts for commonly used actions and settings.
Some important brush settings are displayed here along with global
options like the current foreground and background colors.

## Dockers

There's quite a few dockers available for use that can be toggled on
and off in the `Settings -> Dockers` menu.

Point out the most important dockers: Tool Options, Layers

## Pop-up palette

The pop-up palette appears when you right click on the canvas and
disappears when you click elsewhere.

The pop-up palette gives quick access to colors, brush presets, canvas
rotation, zoom and other settings.

## Canvas-only Mode

Sometimes you might want to hide the controls and just focus on the
canvas. You can achieve this pressing `TAB` to enter "canvas-only
mode". This hides most of the UI elements so the canvas can fill the
whole screen. Pressing `TAB` again goes back to normal.

If you want some controls to stick around in canvas-only mode, you can
configure what gets hidden in the "Canvas-only settings" tab of the
Krita configuration options.

## Rulers and Guides

Click on a ruler and drag toward the canvas to create a guide. Remove
guides by dragging them back.

# Settings and Configuration

Krita has lots of settings, so we won't talk about all of them. But
let me just point out a few important ones:

- If you're looking to map buttons on your tablet/stylus to specific
  actions, you'll probably want to take a look at the canvas input
  settings.
- If you're doing pixel art, you may find it useful to change the zoom
  level where the pixel grid appears: `Display -> Canvas Decorations
  -> Pixel Grid`.
- Check out the `Python Plugin Manager` if you want to use Python
  plugins.

# Brushes

Slide: Discuss dabs, strokes, etc.

## Erasing

Users familiar with other painting programs might expect to find both
a brush tool and an eraser tool. However, Krita doesn't have a
separate eraser tool. Instead, you can erase with the paintbrush tool
by pressing 'E' to toggle "eraser mode".

Brush presets intended to be used as erasers have eraser mode enabled
by default.

Note: If your tablet/stylus has a physically separate eraser tool (or
a button that switches the pen to an eraser), you can assign a brush
preset for each tool independantly.

## Brush Engines

You'll find this is something of a pattern in Krita - tools that
behave like brushes are usually implemented as brushes. Another
example is the clone brush, which paints by copying pixels from
elsewhere in the image.

This flexibility is achieved by having multiple brush engines that
paint in different ways and can be used to achieve different types of
specialized effects.

Example: First sketch a heart shape using the mirror tool. Then create
a pink heart on a red background using the shape brush, which will
automatically fill the heart shape with pink. Enable brush smoothing
to get a smooth heart shape. Then use the Stamp Hearts spray brush to
draw heart stamps all around the pink heart, demonstrating an animated
brush tip. Set the blending mode to luminosity/shine (SAI). Finally,
set a layer style on the pink hearts to add an inner glow.

### Pixel

This is the most common brush engine which represents a standard
pixel-based brush.

- General Brush Settings

#### Masked Brush

The masked brush allows us to combine the properties of two brush
tips, which can be used to create all sorts of unique and interesting
effects.

- Example: Big texture with egg mask
- Example: Watercolor Brushes

### Color Smudge

The color smudge brush engine is similar to the pixel engine, but has
the ability to mix the pigment with the colors already on the canvas.

Most settings behave the same as with the pixel engine, but there are
a few unique settings:

#### Color Rate

#### Smudge Length

1. "Smearing" creates a smearing effect by copying pixels from the
   previous position of the brush to the current position, like
   dragging a finger through wet paint.
2. "Dulling" samples the colors under the brush and mixes it with the
   foreground color, but doesn't create a smearing effect.

Note: Sometimes the "Dulling" option may display a warning ("caution,
pierced brush!"). This indicates the brush tip has a hole or gap that
could cause unexpected results. In practice, I've never found this to
be a problem though.

Since wet brushes are more complex, there's a lot of nuanced settings,
and more details can be found at:
https://docs.krita.org/en/reference_manual/brushes/brush_engines/color_smudge_engine.html

## Brush Settings

Changes made to brush presets are remembered until you either reload
the preset or restart Krita.

To permanently save changes to a preset, click the "Overwrite Brush
Preset" button in the brush settings.

- Color Settings
  - Example: Impressionism Brushes

# Layers and Masks

## Paint Layers

Paint layers are the most common layer type for painting on. These are
basically "exactly what you'd expect" from any standard pixel-based
painting program.

## Group Layers

Group layers are like folders - they contain sets of sublayers or
subgroups. Thus, you can structure your layers as a tree.

You can manipulate group layers using tools like move and transform.
However, you can't paint directly on a group layer.

Group layers are composited together, which is relevant when using
blending modes and alpha inheritance.

## Alpha Inheritance

The small "alpha" icon next to a layer's name toggles "alpha
inheritence". When alpha inheritence is enabled for layer, its content
is "clipped" to content of the layers below it (within the group).

Example: Create a group layer with two children, one has a circle and
the other a square. Enable alpha inheritance on the top layer to
demonstrate. Move the top layer around to demonstrate this is
non-destructive.

## Fill Layers

Fill layers are convenient layers where the content is automatically
generated. For example, a layer that fills the entire canvas with a
single color or a tiled pattern.

Unlike paint layers, fill layers automatically grow and shrink with
the image.

Note: Fill layers are more space-efficient than a regular paint layer
filled with a solid color because they only have one channel.

Example: Generate a fill layer with a pattern fill then resize the canvas.

## Filter Layers

Krita includes lots of filters for creating image effects. While
filters can be applied directly to a paint layer, it's often
convenient to apply a filter non-destructively. Then you can toggle
the filter on or off, experiment with different parameters, etc.

Filter layers apply their effects to the layers underneath them. If
you want to limit the effects to just some layers, use a group layer.

Example: Convert a red apple into a green apple using the `Gradient
Map` filter layer.

## Colorize Mask

The colorize mask is a special type of mask that can be used to
automate coloring in line art.

Example: Color in some pre-existing line-art.

## Vector Layers

Krita supports editing vector shapes in vector layers.

## Transparency Masks

Transparency masks allow you "mask" (hide) portions of a layer
non-destructively.

Transparency masks are grayscale images where black represents full
transparency, white represents full opacity, and shades of gray
represents values in between.

# Selections

- Selection tools
- Local selections
- Edit the global selection

# Painting Assistants

- Parallel Ruler
- Concentric Ellipse
- Perspective and Vanishing Point
- Snap to assistants

Example: Create a box made of bricks

# Resource Management

- Presets
- Patterns
- Bundles
- Vector Shapes

# Vector Tools

- Vector Tools

# Tips & Tricks

- Use '/' to toggle between the two most recently used brushes.
- Resize the brush using shift + drag or '[' and ']'.
- You can save your color palettes inside a KRA file.
- Use the "ten brushes" script to add shortcuts for commonly used presets.
- Use colorize mask to automate coloring line art.
- *.kra and *.bundle files are actually just Zip archives.
- Use the mirror tools or the multibrush tool to create symmetric images.
- Use Wrap Around mode to create tiling images.
  - Example: Create a tiled pattern using the brush smoothing option.
- Zoom out and click the cardinal arrows to expand the canvas.
- Use XNOR blending to get sketches to show up on top of artwork.
- Shortcuts can be key sequences (easier for one-hand use).
- Use the LUT Management docker for a live grayscale view.
- Use the Gradient Map filter to quickly change color schemes.
- Use "Export Advanced" to export scaled versions of an image.

# Resources and Documentation

## Help

- Documentation: [https://docs.krita.org]
- Krita Artists Forum: [https://krita-artists.org]
- IRC: #krita at libera.chat
- Matrix: #krita:kde.org
- Krita users Matrix Channel: #krita-users:kde.org
- Krita YouTube channel: [https://www.youtube.com/@KritaOrgPainting]

## Brushes, Patterns, etc.

- David Revoy's website (https://www.davidrevoy.com) has excellent free bundles.
- Ramón Miranda has created numerous great bundles at https://files.kde.org/krita/extras.
- https://opengameart.org has some good tiling textures with open licenses.
