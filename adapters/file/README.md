# Routing Service Adapters: File 

Example of Routing Service adaptor that can be used to read and write data from files.

The **StreamReader** for the File adaptor reads the data from file specified in the routing service configuration for the adapter. Each line results on a single sample which is read, parsed, and stored into a DynamicData which is then given to the Routing Service.

The **StreamWriter** for the File adaptor receives a DynamicData and writes it into a file specified in the routing service configuration for the adapter. Each sample is wtitten to a line.

The adaptor is written in a generic manner such that it can operate on any data type. It gets the type information from the **DynamicData** and uses the introspection API to determine field names and types.

The data-types can be either discovered from the other side or the route, or else configured on the Routing Service XML configuration.

The file format uses is a set of comma-separated,  name=value pairs. Where each name=value pair represents a field as in:
```
color=RED,x=10,y=20,shapesize=30
```

You can modify the **LineConversion.c** to use a different file format.

