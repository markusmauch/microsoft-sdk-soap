# microsoft-sdk-soap
This project is a fork of the Microsoft Dynamics CRM Sdk.Soap.js library (https://code.msdn.microsoft.com/SdkSoapjs-9b51b99a) with support for Universal Module Definition (https://github.com/umdjs/umd).

## Further Improvements

* Allows to set the value of a Lookup Attribute to null, not just to ``Sdk.EntityReference``.
* Escape illegal XML characters during XML serialization.
* ``contains`` method of ``Sdk.Collection`` optionally takes a filter predicate function as argument.
* ``Sdk.Collection`` has a new method ``select`` which returns a subset of the items satisfying a predicate function.
* ``Sdk.Entity`` has a new method ``containsAttribute`` which checks whether the entity has an attribute that satisfies a predicate function.

## TypeScript definition

There is a TypeScript definition available: https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/microsoft-sdk-soap.

## Usage

### Module name setup

    require.config( {
        paths: {
            // Core library
            "Sdk": "<FilePath>/Sdk.Soap",
            
            // Optional message plug-ins
            "Sdk.RetrieveMetadataChanges": "<FilePath>/Sdk.RetrieveMetadataChanges",
            "Sdk.SetState": "<FilePath>/Sdk.SetState",
            ...
        }
    } );

### Module loading

    define( ["Sdk"], function( Sdk )
    {
        var query = new Sdk.Query.QueryByAttribute( "account" );
        query.addColumn( "name" );
        query.addAttributeValue( new Sdk.String( "accountnumber", "12345" ) );
        Sdk.Q.retrieveMultiple( query );
    } );

Loading optional messages results in a modified Sdk reference:

    define( ["Sdk.RetrieveMetadataChanges"], function( Sdk )
    {
        Sdk.Mdq !== undefined; // true
    } );
