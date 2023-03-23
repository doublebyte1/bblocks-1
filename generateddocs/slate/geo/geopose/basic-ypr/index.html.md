---
title: GeoPose Basic-YPR (Schema)

language_tabs:
  - json

toc_footers:
  - Version 0.1
  - <a href="https://github.com/cportele/ogcapi-building-blocks#building-block-maturity">Maturity</a>: Proposal
  - <a href='#'>{bblock.name}</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: GeoPose Basic-YPR (Schema)
---

# Overview

Basic GeoPose using yaw, pitch, and roll to specify orientation

# Description

GeoPose 1.0 is an OGC Implementation Standard for exchanging the location and orientation of real or virtual geometric
objects (“Poses”) within reference frames anchored to the earth’s surface (“Geo”) or within other astronomical
coordinate systems.

The Basic-YPR Target has a simple structure with no options. Position is specified as a point in an LTP-ENU frame and
rotation is specified by yaw, pitch, and roll angles specified in decimal degrees.

The Basic_YPR.position attribute shall represent the outer frame, specified by an implicit WGS-84 CRS and an implicit
EPSG 4461-CS (LTP-ENU) coordinate system and explicit parameters to define the tangent point.

The Basic_YPR.angles attribute shall represent the inner frame, which is a rotation-only transformation with Yaw, Pitch,
and Roll (YPR) angles, which expressed as three consecutive rotations of a reference frame oriented East-North-Up (ENU)
coordinate system (where the coordinate axes East, North, and Up correspond to the axes X, Y, Z) about the local (
rotated) axes z, y, and x, applied in that order, corresponding to the conventional Yaw, Pitch, and Roll angles. The
unit of measure SHALL be the degree and the angles represented as signed real number values.

# Examples

## Example
```json
{
  "position": {
    "lat": 47.7,
    "lon": -122.3,
    "h": 11.5
  },
  "angles": {
    "yaw": 5.514456741060452,
    "pitch": -0.43610515937237904,
    "roll": 0.0
  }
}
```
```json
{
  "position": {
    "lat": 47.7,
    "lon": -122.3,
    "h": 11.5
  },
  "angles": {
    "yaw": 5.518671098486835,
    "pitch": -0.4381464123477409,
    "roll": 0.0
  }
}
```
# Schema

[schema.yaml](https://raw.githubusercontent.com/rob-metalinkage/bblocks/v3registry/registereditems/geo/geopose/basic-ypr/schema.yaml)

```yaml
"$schema": https://json-schema.org/draft/2020-12/schema
description: 'Basic-YPR: Basic GeoPose using yaw, pitch, and roll to specify orientation'
'@modelReference': ../context.jsonld
type: object
properties:
  position:
    "$ref": ../position.schema.yaml
  angles:
    "$ref": ../angles.schema.yaml
required:
  - position
  - angles

```
# Sources

* [OGC GeoPose 1.0 Data Exchange Draft Standard](https://docs.ogc.org/dis/21-056r10/21-056r10.html)