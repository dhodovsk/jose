jose-jws-fmt(1) -- Converts a JWS between serialization formats
===============================================================

## SYNOPSIS

`jose jws fmt` -i JWS [-I PAY] [-o JWS] [-O PAY] [-c]

## OVERVIEW

The `jose jws fmt` command converts a JWS into alternative serialization
formats. For example, it can:

1. Attach payload to a detached JWS.
2. Detach payload from a JWS.
3. Convert JWS Compact Serialization to JWS JSON Serialization.
4. Convert JWS JSON Serialization to JWS Compact Serialization.

## OPTIONS

*  `-i` _JSON_, `--input`=_JSON_ :
  Parse JWS from JSON

*  `-i` _FILE_, `--input`=_FILE_ :
  Read JWS from FILE

*  `-i` -, `--input`=-:
  Read JWS from standard input

*  `-I` _FILE_, `--detached`=_FILE_ :
  Read decoded payload from FILE

*  `-I` -, `--detached`=- :
  Read decoded payload from standard input

*  `-o` _FILE_, `--output`=_FILE_ :
  Write JWS to FILE

*  `-o` -, `--output`=- :
  Write JWS to stdout (default)

*  `-O` _FILE_, `--detach`=_FILE_ :
  Detach payload and decode to FILE

*  `-O` -, `--detach`=- :
  Detach payload and decode to standard output

*  `-c`, `--compact` :
  Output JWS using compact serialization

## EXAMPLES

Attach payload to a detached JWS and emit JWS Compact Serialization:

    $ jose jws fmt -i msg.jws -I msg.txt -o compact.jws -c

Detach payload from a JWS:

    $ jose jws fmt -i msg.jws -o detached.jws -O msg.txt

## AUTHOR

Nathaniel McCallum &lt;npmccallum@redhat.com&gt;

## SEE ALSO

`jose-jws-sig`(1),
`jose-jws-ver`(1)
