# Bitmoji Runner Pro — playable WebGL prototype

This is a playable 3D WebGL endless runner with three lanes, swipe controls, jump, slide, collectible gems, obstacles, three lives and sound effects. It works in a modern browser and does not use external runtime resources.

## SNAPCHAT INTEGRATION NOT COMPLETE
This is **NOT** the final upload-ready, real 3D Bitmoji Lens. The original 3D runner is a procedurally assembled fallback avatar. The production version must load the player's Snapchat rigged GLB from `snapchat.bitmoji.get3DAvatar()` into a proper GLB loader/renderer, then apply **animations authored against Snap's rig**, as described in the official Bitmoji docs. The current rendering engine uses only procedural cube/sphere meshes, and cannot load rigged GLB models.

`./snap-api.js` is an empty placeholder, **not the official Snap package**. Replace with `dist/snap-api.js` from the official `@snap/web-lens-api` npm package and repackage before Snapchat submission. The code then checks `init()`, supports native scores with `submitScore()`, opens native leaderboard via `show()`, loads the player's actual Bitmoji **portrait image** through `get2DAvatar()` for UI and calls native `storage.get/set` for the personal best. Those features require in-Snap runtime testing. In standalone browsers, the player remains the fallback and best score is stored locally.

Note: the official Web Lens browser stub does not supply a real 3D Bitmoji; testing requires an approved Lens on Snapchat. The official leaderboard must be configured for that Lens.

## Folder layout
`index.html`, `game.js`, `snap-api.js`, `README.md`.

## Zip rules
The ZIP has `index.html` at its root and relative paths. It does not contain dependencies from a CDN.

## How to test
Open index.html on a local static server (such as GitHub Pages) on mobile; press Play, swipe sideways, up to jump, down to slide.
