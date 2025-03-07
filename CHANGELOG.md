Changelog
=========

3.4
---

  * compatibility with yojson 1.6.0
    (#90, #92)
    Vadim Radovel and Nathan Rebours

3.3
---

  * Make `_exn` functions opt-in (`[@@deriving yojson { exn = true }]`)
    to preserve backward-compatibility for fully-manual implementations
    of the [@@deriving yojson] interface.
    (#86)
    Gabriel Scherer

3.2
---

  * Add `let _ = to_yojson / of_yojson` to generated code to avoid warnings when
    they aren't used
    (#68)
    Steve Bleazard
  * Fix bug where doing [@@deriving of_yojson] causes an unused rec warning
    (#68)
    Steve Bleazard
  * Add generated `ty_of_yojson_exn` to raise an exception rather than return an
    error
    (#57, #68)
    Steve Bleazard
  * Port `ppx_deriving_yojson` to `dune`
    (#69, #85)
    Rudi Grinberg, Antonio Nuno Monteiro
  * Added deriver option `fields` to generate a `Yojson_meta` module containing
    all JSON key names.
    (#70)
    Steve Bleazard
  * Remove cppo that included support for versions no longer supported by
    `ppx_deriving_yojson`
    (#75)
    Rudi Grinberg

3.1
---

  * Fix ppx_deriving_yojson.runtime META file
    (#47)
    Étienne Millon
  * Support for inline records in variant types
    (#50)
    Gerd Stolpmann
  * OCaml 4.06 compatibility
    (#64, #66)
    Leonid Rozenberg, Gabriel Scherer

3.0
---

  * Use Result.result in generated code.
  * Compatibility with statically linked ppx drivers.
  * OCaml 4.03 compatibility.

2.3
---

  * Adapt to syntactic changes in 4.02.2.
  * Improve compatibility with libraries that shadow modules
    from standard library, such as Core.
  * Allow deserializing float values that appear as integer
    literals in the input JSON.
  * Suppress some warnings.

2.2
---

  * Add support for open types.

2.1
---

  * Handle inheriting from a parametric polymorphic variant type.
  * Don't leak type variables.

2.0
---

  * Update to accomodate syntactic changes in _deriving_ 1.0.
  * Common helper functions have been extracted into
    ppx_deriving_yojson.runtime, reducing code size.
  * Add support for `[@@deriving to_yojson, of_yojson]`
    and `[%to_yojson:]`, `[%of_yojson:]` shortcuts.
  * Add support for `[@@deriving yojson { strict = false }]`.

1.1
---

  * Add `[@key]`, `[@name]` and `[@default]` attributes.
  * Add support for `Yojson.Safe.json` values.

1.0
---

  * Initial release.
