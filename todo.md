# TODO

- Manual style consistency check:
  Confirm whether usages like `*VRButton.createButton()*`, `*window.requestAnimationFrame()*`, and `*dispose()*` in manual pages are intentional emphasis, or unintended style inconsistency vs backtick code style.
  Scope to verify first:
  - `manual/en/how-to-create-vr-content.html`
  - `manual/en/how-to-dispose-of-objects.html`
  - `manual/zh/how-to-create-vr-content.html`
  - `manual/zh/how-to-dispose-of-objects.html`

- Terminology consistency check (`后处理` vs `后期处理`):
  Decide one preferred translation for "post-processing" in zh manual and apply consistently to titles/body text.
  Initial hotspots:
  - `manual/zh/how-to-use-post-processing.html`
  - `manual/zh/post-processing.html`
  - `manual/zh/webgpu-postprocessing.html`
  - `manual/zh/color-management.html`
  - `manual/zh/how-to-dispose-of-objects.html`
  Note:
  - Newly added 10-page set has been partially normalized to `后处理`.
  - Cross-page inconsistency still exists in legacy pages and menu labels; plan a follow-up pass for full zh manual alignment.

- Terminology consistency check (`fov` translation):
  Decide one preferred translation between `视野范围` and `视场`, then apply consistently in zh manual while keeping API names unchanged.
  Initial hotspots:
  - `manual/zh/cameras.html`
  - `manual/zh/fundamentals.html`
  - `manual/zh/creating-a-scene.html`
  - `manual/zh/faq.html`
  - `manual/zh/how-to-update-things.html`
