# Garden Schema

JSON Schema specification for modeling ecosystems as composable directed graphs.

## Structure

```
garden.schema.json          # Root schema
slices/
├── core.schema.json         # Name, description, version, timestamps (required)
├── sprouts.schema.json      # Products and services
├── maintainers.schema.json  # Garden maintainers
├── theme.schema.json        # Visual theming
└── composition.schema.json  # Subgardens, supergardens
```

## Slices

| Slice | Required | Description |
|-------|----------|-------------|
| core | Yes | Garden identity: name, description, version, timestamps |
| sprouts | No | Products and services in the garden |
| maintainers | No | People who maintain the garden |
| theme | No | Visual theming for rendering |
| composition | No | Garden hierarchy (subgardens, supergardens) |

## Usage

```json
{
  "$schema": "https://garden.omni.dev/garden.schema.json",
  "version": "1.0.0",
  "core": {
    "name": "My Garden",
    "description": "An ecosystem of tools"
  },
  "sprouts": [
    {
      "name": "My App",
      "homepageUrl": "https://myapp.dev"
    }
  ]
}
```

## Validation

```bash
npx ajv validate -s garden.schema.json -d examples/minimal.json
```

## License

The code in this repository is licensed under Apache 2.0, &copy; [Omni LLC](https://omni.dev). See [LICENSE.md](LICENSE.md) for more information.
