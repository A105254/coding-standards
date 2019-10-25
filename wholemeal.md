# Best practices followed by Wholemeal team to develop solution using C# .NET and cloud computing using CICD pipeline

## DevOps

1) GitHub:
 a) repo name: organization_name.component.sub-component
 b) branch: master and develop. (pull request raised from develop to master)
 c) release: V[#newfunctionality][#bugfixes][#features]
 d) teams(access): Wholemeal(write), Wholemeal Admins(admin),Wholemeal_Vsts_Admin(admin),All-Repos-RO-access(read)
 e) commits: [Jira Card number] - [statement].
 f) pull request getting raised on master from dev branch and getting merged with master after the request gets approved.

2) Azure DevOps:
 a) vsts build: [release-version-from-github].[vsts.Build.BuildNumber]
 b) vsts release: [vsts.Build.BuildNumber].[yyyyMMdd].[vsts.Release.ReleaseId]
 c) Changes only from the dev branch will get deployed in dev environment.
 d) Changes only from the master branch will get deployed in test and production environment.


## Azure Components

1) Resource Group: [component]-[subcomponent]-[environment]-[subenvironment]-rg
2) App Service Plan: [component]-[subcomponent]-asp-[environment]-[subenvironment]
3) Storage Account: [component][subcomponent][environment][subenvironment]sa
4) Key Vault: [component]-[subcomponent]-[environment]-[subenvironment]-kv
5) Function App: [component]-[subcomponent]-[environment]-[subenvironment]-funcapp
6) App Insights: [component]-[subcomponent]-app-ins-[environment]-[subenvironment]
7) Action Groups: [component]-[subcomponent]-[environment]-[subenvironment]-action-group

## Development

1) Private field    : _lower Camel Case
2) Public field     : Upper Camel Case
3) Protected field  : Upper Camel Case
4) Internal field   : Upper Camel Case
5) Property         : Upper Camel Case
6) Method           : Upper Camel Case
7) Class            : Upper Camel Case
8) Interface        : IUpper Camel Case
9) local variable   : lower Camel Case
10) Parameter       : lower Camel Case



## Unit Testing

1) Using Xunit tool for unit testing.
2) Using Nsubstitute nuget package to mock the dependencies.
3) Try to use FluentAssertions when writing unit tests.
4) Method Name based on test cases: MethodName_StateUnderTest_ExpectedBehavior, Should_ExpectedBehavior_When_StateUnderTest
5) It is integrated with the CI pipleine so that if it fails release pipeline won't start.


## Integration Testing

1) Using separate solution for the Integration test project for each service.
2) Use BDDFy framework with Xunit tool for the test cases.
3) Using Nsubstitute nuget package to mock the dependencies.
4) Method Name based on test cases: MethodName_StateUnderTest_ExpectedBehavior, Should_ExpectedBehavior_When_StateUnderTest
5) It is integrated in most of the API's release pipeline. After code deployment gets completed it will build and run the integration test project in release pipeline.
6) This is happening in dev and test environment.
