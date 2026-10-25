# Unofficial Plants vs Zombies 2 Mappings

## PvZ2 Mapping File Format Specification

### Structure & Class Definitions

```
CLASS    <OFFSET>       <new IDENT>
  FIELD  <STARTING OFFSET> <TYPED_IDENT>
  VFUNC  <INDEX> <OFFSET> <TYPED_IDENT>
    <Function Context>
  FUNC   <OFFSET> <TYPED_IDENT>
    <Function Context>
```

### Global Definitions
```
DAT   <OFFSET> <TYPED_IDENT>
PTR   <OFFSET> <TYPED_IDENT>
SFUNC <OFFSET> <TYPED_IDENT>
  <Function Context>
```

### Function Context

```
  PARAM  <INDEX> <TYPED_IDENT>
  LOCAL  <old IDENT> <TYPED_IDENT>
```

### Primitives & Tokens

```
<TYPED_IDENT>      = <TYPE> <new IDENT>
<TYPE>             = <CLASS> | <GHIDRA BUILTIN TYPE>
<IDENT>            = [a-zA-Z0-9_]+
<OFFSET>           = [0-9a-fA-F]{8}  (or hex offset representation)
<STARTING OFFSET>  = 0x[0-9a-fA-F]+
<INDEX>            = [0-9]+
```