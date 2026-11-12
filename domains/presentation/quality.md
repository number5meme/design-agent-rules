# Presentation Acceptance

Read by task: [Workflow](workflow.md) · [Method](design.md) · [Acceptance](quality.md). For local edits, read only the affected sections.

Check numeric thresholds for text and key graphics, final-size determination, and print/projection boundaries per the [static visuals readability baseline](../../standards/defaults.md#static-visuals); record color measurements and the actual output environment, and do not pass based on subjective readability alone.

Apply together with [Design File and Export Acceptance](../../standards/quality.md#design-file-and-export-acceptance), checking according to the scope of this change:

- Content: slide count, order, and required content match the scope; titles correspond to evidence; data, citations, and chart bases are consistent; assumptions are not written as facts.
- Whole deck: view a rendered overview of all slides, check rhythm, layouts, type hierarchy, semantic colors, and repeated elements, and locate anomalies to specific slides.
- Single slide: view text and charts at a readable size, checking line breaks, overflow, occlusion, clipping, distortion, and contrast. View complex slides and slides the overview cannot judge at full resolution; do not pass based on thumbnails alone.
- Editability: when editability is agreed, actually check required objects such as text, shapes, and charts; full-slide images cannot replace these objects. Check converted files against the originals for losses.
- Final file: reopen or render the export in an environment that supports the target format, checking font substitution, pagination, and assets; when there are links, animations, notes, or media, check the corresponding behavior. A valid file structure does not mean display and playback in the target software are verified.
- Revisions: re-render changed slides and check affected shared layouts and related slides. After the final export changes, recheck the corresponding results, and state unverified environments and capabilities.

When delivering a project source, check that resource references are complete and paths are portable; check font embedding per licensing and tool support, and do not treat an enabled export option as successful embedding.
