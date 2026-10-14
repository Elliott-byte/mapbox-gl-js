# This is the Mapbox GL JS repository

Include all info from the @CLAUDE.md file.

## Cursor Cloud specific instructions

- Node comes from `.nvmrc` via nvm and is prepended in `~/.bashrc` so it wins over `/exec-daemon/node`.
- `npm start` (tmux session `mapbox-dev`) serves the debug catalog at http://localhost:9966/debug/. Use the hostname `localhost`. The committed debug token is URL-restricted, so opening the same pages on `127.0.0.1` returns 403 for vector tiles.
- `MAPBOX_ACCESS_TOKEN` is optional. Debug pages fall back to the localhost token in `test/util/access_token.js`.
- Render tests on this host need `CI=true` (`CI=true npm run test-render -- -t "background-color/default"`). Without it, Chrome launches headed with `--use-angle=gl` and no `--ignore-gpu-blocklist`, and WebGL context creation fails on the software GPU.
