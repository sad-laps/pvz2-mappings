# Unofficial Plants vs Zombies 2 Mappings

## PvZ2 Mapping File Format Specification

### Structure & Class Definitions

```
CLASS    <IDENT> <SIZE>
  FIELD  <STARTING OFFSET> <TYPED_IDENT>
  VAR    <OFFSET> <TYPED_IDENT>
  VTABLE <OFFSET> <(parent vtable)IDENT> <IDENT> <SIZE>
    VFUNC <INDEX> <OFFSET> <TYPED_IDENT>
      <Function Context>
  FUNC   <OFFSET> <TYPED_IDENT>
    <Function Context>
```

### Global Definitions
```
PTR   <OFFSET> <TYPE>
SVAR  <OFFSET> <TYPED_IDENT>
SFUNC <OFFSET> <TYPED_IDENT>
  <Function Context>
```

### Function Context

```
  PARAM  <INDEX> <TYPED_IDENT>
  LOCAL  <(old)IDENT> <TYPED_IDENT>
```

### Tokens

```
<TYPED_IDENT>      = <TYPE> <IDENT>
<TYPE>             = <CLASS> | <GHIDRA BUILTIN TYPE>
<IDENT>            = [a-zA-Z0-9_]+
<OFFSET>           = [0-9a-fA-F]{8}  (or hex offset representation)
<STARTING OFFSET>  = 0x[0-9a-fA-F]+
<INDEX> / <SIZE>   = [0-9]+

# EXTRAS

<WILDCARD>    = <> # Unmapped, skip if used in place of a token
```