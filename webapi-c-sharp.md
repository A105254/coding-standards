# Best practices to follow for WebAPI development using C# .NET

## Development

1) Smaller functions: Functions must be within 20 lines and serve only one purpose.
2) Single purpose class: Classes must have single purpose as well.
3) FluentValidations validate any incoming request to API based on custom rules written by developer.
4) Focus on readability. Classes, functions and variables must have names which describe what they do clearly.
5) Functions must start with a verb e.g. GetAccountNumber.
6) Do not create objects inline. Consider using builder pattern or parameterized constructor with guard clauses to prevent invalid object creation.
7) Try configuring global exception handling in the solutions. Refer to Stored Payments API startup.cs for any details.
8) Consider using enums or const variables for any constant value.
9) Do not check-in any changes made in the local web.config unless it is new addition.
10) Consider using IEnumerable over Lists for deferred execution benefits.
11) If a parameterized constructor is created for a table entity, please provide a parameterless constructor as well. Otherwise, autofac will fail to register the repository as there is a constraint on the Generic TableRepository type where the Generic type must have a parameterless constructor. Please refer the AzureStorage solution for more details.
12) In general avoid writing static classes and functions as they cannot be extended. In case of helpers/utilities they are fine.
13) Keep most of the logger level as Debug. Keep the entry and exit point of a function as Information to keep logs low in number.
14) Replace object creation to inline values if it is used only once
15) Null check always for config values, function parameters and inputs
16) Remove any unused references, functions and variables
17) Keep variables inside the block where they are used
18) No empty file in solution


## Testing

1) Try to write more e2e tests as opposed to unit tests as they check the overall functionality
2) Try to use FluentAssertions when writing unit tests
3) Use NBuilder to create dummy objects to be used during testing
4) Try to do more behavioral tests
