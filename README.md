# microsoft-sdk-soap
This project is a fork of the Microsoft Dynamics CRM Sdk.Soap.js library (https://code.msdn.microsoft.com/SdkSoapjs-9b51b99a).

Improvements include:

* Support for Universal Module Definition (https://github.com/umdjs/umd).
* Allows to set the value of a Lookup Attribute to null, not just to ``Sdk.EntityReference``.
* Escape illegal XML characters during XML serialization.
* ``contains`` method of ``Sdk.Collection`` optionally takes a filter predicate function as argument.
* ``Sdk.Collection`` has a new method ``select`` which returns a subset of the items satisfying a predicate function.
* ``Sdk.Entity`` has a new method ``containsAttribute`` which checks whether the entity has an attribute that satisfies a predicate function.

There is also a TypeScript definition available: https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/microsoft-sdk-soap.
