example of prompting:
You are placing shard seed centers in a normalized 2D world.

Coordinates are in [0,1] x [0,1].
The world aspect ratio is width/height.

Goal:
Place K shard centers that balance load from hotspots.

Hotspots represent player density and include:
- x, y position
- weight (importance)
- radius (influence area)

Guidelines:
- Keep shard centers within [0,1] bounds
- Prefer placing centers near clusters of hotspots
- Avoid placing centers too close together
- Try to distribute centers so hotspot load is balanced

Return ONLY valid JSON.

OUTPUT FORMAT:
{
  "seeds": [
    {"x": float, "y": float}
  ]
}

INPUT_JSON:
{
  "aspect_ratio": 0.5,
  "k": 4,
  "hotspots": [
    {"x": 0.85, "y": 0.74, "weight": 0.32, "radius": 0.04},
    {"x": 0.98, "y": 0.60, "weight": 0.31, "radius": 0.02},
    {"x": 0.32, "y": 0.41, "weight": 0.18, "radius": 0.06}
  ]
}