# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/).

## [Unreleased][2.0] - 2019-XX-XX

### Added

- Introduce `VisualAccidentalNoise` editor plugin.
  - Expose and add most visual noise nodes according to `AccidentalNoise` class.
  - Add component visual noise nodes to create more complex noise from base ones.
  - Ability to save and load visual noise and components as resource.
- Expose normalmap and bumpmap noise mapping methods.
- Add noise formats: heightmap, normalmap, bumpmap, texture.
- Add methods to map noise to 3D image, including seamless (experimental, internal only).
- Add methods to generate seamless 2D/3D noise regardless of mapping mode.
- Add convenience methods to get noise via `Vector2`/`Vector3`.
- Define expression as property from which noise can be evaluated if set (unstable).
- Expose methods for programmable noise via variables.
- Document more methods and members.

### Changed

- Rename `AnlNoise` class to `AccidentalNoise` throughout the module.
- Make `AccidentalNoise` extend a `Resource` so that in can be saved on disk.
- Rewrite methods for retrieving noise and instruction indexes via `function` property from which the noise is evaluated.
- Rewrite noise image mapping and expose mapping mode and ranges as properties.
  - `map_to_image` is used internally, set noise parameters via exposed properties and use `get_image` instead.
- Mapping ranges changed to `AABB` instead of `Rect2` to include 3D noise mapping.
- Rewrite `ExpressionBuilder` to use *snake_case* style by default, *camelCase* can be toggled before build.

### Fixed

- Slightly optimize noise image mapping performance for RGBA8.
