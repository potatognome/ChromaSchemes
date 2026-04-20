## Purpose
Chromaschemes is the geometric colour‑scheme engine for Chromaspace.
It generates structured colour schemes based on:
- Geometric parameters
- Colour‑space definitions
- Chromaspace primitives
Chromaschemes must register all scheme generators with the Chromacore Registry.

Project Structure
Chromaschemes/
    src/chromaschemes/
        generators/
        geometry_extensions/
        loaders/
        integration/
    config/
        CHROMASCHEMES_CONFIG.json
        CHROMASCHEMES.d/
    docs/
    tests/



Registry Integration
Copilot must ensure:
- All scheme generators use @register_scheme
- Metadata is complete and validated
- Config schemas are declared
- Capabilities are explicit (e.g., ["circular", "rotational"])
Example:
@register_scheme(
    name="orbit",
    version="1.0",
    capabilities=["circular", "rotational"],
    config_schema="schemas/orbit.yaml",
)
class OrbitSchemeGenerator(SchemeInterface):
    ...



tUilKit Integration
Copilot must:
- Use tUilKit config loader
- Support .d override directories
- Use structured logging
- Produce deterministic scheme outputs

Geometry Extensions
Copilot may add new geometry primitives under:
geometry_extensions/


These must integrate with Chromaspace geometry.

Testing
Copilot must scaffold:
- Generator tests
- Config loading tests
- Deterministic output tests
