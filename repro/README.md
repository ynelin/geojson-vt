# Polygon winding after quantization: visual reproduction

Supporting images for https://github.com/maplibre/geojson-vt/pull/261.

These comparisons show machine-track coverage rendered with MapLibre GL JS 6.16.0. Original rendering is on the left; the proposed fix is on the right. Both use the same geometry, camera settings and zoom sequence.

- `coverage-comparison.gif`: before/after rendering across zoom transitions near zoom 13 and 14.
- `coverage-comparison.png`: static comparison at zoom 14.

The candidate TypeScript patch was compiled and its coordinate transform substituted into an isolated MapLibre worker for the browser checks. Its raster output matched the initial prototype across all 152 captured samples. This was an AI-assisted investigation; the change is proposed for maintainer review and discussion, not as a universal topology repair. Small quantization artifacts remain.

The implementation and synthetic regression tests are in the pull request. This separate branch only hosts the supporting images so they are not part of the code-change diff.
