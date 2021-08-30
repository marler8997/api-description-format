Api Description Format
================================================================================
An exploration on a format to describe library APIs. The idea is that you could
describe your API in this format and use tools to generate bindings for that API
in different languages.


Initial Design
================================================================================
For now I'm going to leverage JSON to store this format. JSON is simple,
however, for a human maintained documents it has some limitations such as lack
of comments and being overly strict/verbose, but it's good for a first draft
due to its simplicity.


This is the initial design for the API format given as a set of object
definitions.  Each file will contain a `Root` object in this format:


`Root`:
```
{
    "Constants": [<Constant>...]
    "Types": [<TypeDefinition>...]
    "Functions": [<Function>...]
}
```

`Constant`:
```
{
    "Versions":[<version>...],
    "Name":"<name>",
    "Type":<TypeReference>,
    "Value":<Value>
}
```

`TypeReference`:
```
{"Kind":"Integer","Signed":true,"Width":32}
```

`Value`:
```
{"Kind":"Integer","Value":1234}
```

`TypeDefinition`:
```
{
    "Versions":[<version>...],
    "Name":"<name>",
    ...
}
```

`Function`:
```
{
    "Versions":[<version>...],
    "Name":"<name>",
    ...
}
```
