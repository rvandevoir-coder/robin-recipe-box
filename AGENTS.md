# Robin Recipe Box production workflow

This repository is the editable production source for Robin's Recipe Box.

## Production
- Live site: https://robin-recipe-box.netlify.app/
- Production branch: `main`
- Static publish directory: repository root (`.`)
- Main site file: `index.html`

## Recipe commands
When Robin asks to "save this recipe", "update this recipe", "delete this recipe", or similar:

1. Read the latest `index.html` from `main` before editing.
2. Preserve every recipe not explicitly requested to change.
3. Add or update only the requested recipe.
4. Use a stable recipe `id`; update by that id instead of duplicating.
5. Default finalized recipes to `Keeper` unless Robin says they are still testing.
6. Increment `CONTENT_VERSION` whenever a newly published built-in recipe must be delivered to browsers that already have local storage.
7. Keep the local-storage merge behavior: new published recipes may be added to an existing browser collection, but existing browser-saved recipes/edits must not be erased.
8. Commit directly to `main` with a clear message such as `Add crab leg recipe` or `Update convection chicken thighs`.
9. Do not create a second Netlify site or change the public URL.
10. Do not modify the original OneDrive cookbook backup.

## Important
GitHub is the editable production copy. The OneDrive cookbook backup is read-only and must remain untouched.

Do not make unrelated design changes when the request is only to save or update a recipe.
