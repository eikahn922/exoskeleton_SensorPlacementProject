# CAD Design History

The design folders follow chronological development order, not the overlapping numbers used in the original Drive folder.

| Folder | Original source | Contents |
| --- | --- | --- |
| `Design 1` | `Design 1` | Initial housing, hinged-lid concept, electronics references, and assembly |
| `Design 2` | `Design 1, Part 2` | Revised housing and assembly |
| `Design 3` | `Design 2` | Second numbered Drive iteration |
| `Design 4` | `Design 3` | CAN Pal integration and third numbered Drive iteration |
| `Final` | `FINAL DESIGN` | Original ZIP plus an extracted copy for easier review |
| `Lid Tests` | `Lid Test 1` | Snapping-lid test models |

## Working with the files

- SolidWorks part and assembly filenames are preserved from the source.
- Assemblies may depend on relative references. If SolidWorks reports missing components, relink them to the matching part in the same design folder rather than substituting a part from another generation.
- The final ZIP is retained unchanged under `Final/Source Archive`; its contents are also available under `Final/Extracted CAD`.
- Treat earlier generations as design history; `Final` is the completed and validated baseline for the intended project configuration.
