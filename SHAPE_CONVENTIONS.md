# Shape Naming and Style Conventions

Use this guide when adding new entries to `classical-mechanics.xml`.

## 1) ID Naming

- Format: `category_object[_variant]`
- Lowercase with underscores only.
- Keep IDs stable once published.
- Examples:
  - `force_tension`
  - `support_roller`
  - `system_atwood`
  - `vector_force_large`

## 2) Display Name and Value

- `name`: human-readable label shown in shape library.
- `value`: short token used inside diagram instances.
- Keep them aligned with ID semantics.
- Prefer singular nouns unless shape clearly represents a system.

Examples:

- `id="vector_force" name="Force Vector" value="force"`
- `id="system_pendulum" name="Pendulum System" value="pendulum"`

## 3) Title Field

- `title` should describe intent, not implementation details.
- Write as short tooltip text (5-10 words).
- Example: `title="Support reaction upward"`

## 4) Geometry Defaults

- Use predictable defaults to make drag-drop behavior consistent.
- Suggested defaults:
  - Vector shapes: `100x100`
  - Point or node symbols: `30x30` to `50x50`
  - Beams/surfaces: wide and shallow (`120x20` range)
- For directional vectors, set explicit source and target points.

## 5) Style Patterns

- Use semicolon-separated key-value pairs with no extra spaces.
- Maintain consistent stroke widths for similar classes:
  - Primary force vectors: `strokeWidth=2` to `2.5`
  - Emphasis/resultants: `strokeWidth=3`
  - Reference guides: `strokeWidth=1` to `1.5`
- Use dashed patterns intentionally:
  - Kinematic guides/trajectories: dashed
  - Physical applied forces/components: mostly solid

## 6) Color Semantics (Recommended)

- Forces: red/green/orange family
- Kinematics (velocity/displacement): blue family
- Rotational indicators: orange/magenta family
- Constraints/supports: grayscale or muted tones

This keeps diagrams visually scannable.

## 7) Section Placement

Add new cells under the nearest section header in `classical-mechanics.xml`:

- FORCE VECTORS
- MASS AND MECHANICAL ELEMENTS
- CONSTRAINTS AND CONNECTIONS
- KINEMATICS AND REFERENCE MARKERS
- COMMON SYSTEM TEMPLATES
- ADVANCED FORCES AND DECOMPOSITION
- ANNOTATION AND LABELING
- ALTERNATE BASIC PRIMITIVES

If needed, add a new section with the same comment header style.

## 8) Change Safety

Before committing changes:

1. Run the `Validate draw.io XML` task.
2. Import the updated XML in draw.io and drag at least one new shape.
3. Confirm existing IDs were not renamed.
