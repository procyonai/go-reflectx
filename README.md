# reflectx

The sqlx package has special reflect needs.  In particular, it needs to:

* be able to map a name to a field
* understand embedded structs
* understand mapping names to fields by a particular tag
* user specified name -> field mapping functions

The first two are amply taken care of by `Reflect.Value.FieldByName`, and the third is
addressed by `Reflect.Value.FieldByNameFunc`, but these don't quite understand struct
tags in the ways that are vital to most marshalers, and they are slow.

This reflectx package extends reflect to achieve these goals.
