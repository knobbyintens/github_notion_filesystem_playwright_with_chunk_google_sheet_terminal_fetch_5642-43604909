# Delivery Kit - Package Acceptance Checklist

This repository is the shared delivery kit for the Content Operations
program. Contributors work on their own branch and place every newly
delivered package under `contributions/<handle>/<package>/`.

A package is accepted only when every requirement below passes.

## Documentation content checks

1. `README.md` must exist, must contain visible text, and must contain
   English text only.
2. `RELEASE_NOTES.md` must exist, must contain visible text, and must
   contain English text only.
3. `NOTES.md` is optional. When it is present and non-empty it must contain
   English text only. An empty or absent `NOTES.md` is acceptable.

English text only means that every visible character is printable ASCII
(codepoints 0x20 through 0x7E). Line breaks and tabs are allowed. Any
character outside that range (for example CJK, Cyrillic, Arabic or accented
letters) fails the check. Non-empty means that the file contains at least one
non-whitespace character.

## Structural checks (existence only)

4. `verification/run_checks.py` must exist at exactly this relative path.
   Only the existence of this file is checked. Its contents are not reviewed
   and must not be executed as part of the acceptance decision.
5. The `verification/` directory itself may contain any other files; those
   files are never inspected.

## Result values

Use `complete` when every requirement above passes. Use `in progress` when
any single requirement fails. A package that fails only the structural check
is still `in progress`.

When a requirement fails, report the matching failure code in your audit
record. Use these codes exactly:

| Failure code | Requirement that failed |
| --- | --- |
| `readme_empty` | README.md missing or contains no visible text |
| `readme_not_english` | README.md contains non-English characters |
| `release_notes_empty` | RELEASE_NOTES.md missing or contains no visible text |
| `release_notes_not_english` | RELEASE_NOTES.md contains non-English characters |
| `notes_not_english` | NOTES.md is non-empty and contains non-English characters |
| `missing_verification_script` | verification/run_checks.py is absent |

Contributor-side files such as `package_meta.json` are self-reported and are
never acceptance evidence.

`template/reference-package/` is a complete example of the expected layout.
