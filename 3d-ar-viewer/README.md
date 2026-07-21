# SPECIMEN — 3D / AR Model Viewer

A single-page site for viewing `.glb` / `.gltf` 3D models in-browser and in AR
on mobile, built on Google's [`<model-viewer>`](https://modelviewer.dev/) web
component. No build step, no dependencies to install — just static files.

## Files

- `index.html` — the viewer app (everything: markup, styles, JS)
- `donut.glb` — a sample test model (a simple torus)

## Deploy with GitHub Pages

1. Create a new GitHub repo (e.g. `3d-ar-viewer`) and push these files to it:

   ```bash
   git init
   git add .
   git commit -m "Initial commit: 3D/AR viewer"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/3d-ar-viewer.git
   git push -u origin main
   ```

2. On GitHub, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Set branch to `main` and folder to `/ (root)`, then **Save**.
5. GitHub will publish the site at:

   ```
   https://YOUR-USERNAME.github.io/3d-ar-viewer/
   ```

   It usually takes a minute or two to go live after the first push.

## Why hosting matters for AR

AR mode (Scene Viewer on Android, Quick Look on iOS) **will not launch from a
local file opened as `file://...`** — it requires the page to be served over
`https://`. GitHub Pages serves everything over HTTPS automatically, so once
deployed there, the AR button will work correctly on phones. Opening
`index.html` directly on your computer still works fine for the plain 3D
viewer, just not AR.

## Using it

- Open the deployed link on your phone or computer.
- Drag a `.glb`/`.gltf` file onto the viewer, or click **SELECT FILE**.
- Use mouse/trackpad or touch to orbit, zoom, and pan the model.
- On a supported phone, tap **VIEW IN YOUR SPACE** to place the model in AR.

## Notes

- `.glb` is recommended over `.gltf` for anything loaded via drag-and-drop —
  `.glb` is a single self-contained file, while `.gltf` often references
  separate texture files by relative path, which won't resolve for a
  locally-dropped file.
- To swap in your own default model, replace `donut.glb` and update the file
  name anywhere it's referenced, or just let visitors upload their own model
  through the UI.
