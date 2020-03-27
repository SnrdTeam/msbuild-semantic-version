# Adeptik Semantic Version support

Adeptik Semantic Version support for C# projects.

![Build status](https://tfs.adeptik.com/Adeptik/_apis/public/build/definitions/5f6da651-409b-4516-b0c6-16518d60e6e9/142/badge)
![Nuget (with prereleases)](https://img.shields.io/nuget/vpre/Adeptik.SemanticVersion)

## Version in .NET Core project

To install the version in .NET Core, you can use the following code in the csproj project:

```xml
<PropertyGroup>
    <VersionPrefix>1.0.0</VersionPrefix>
    <VersionSuffix>preview-label</VersionSuffix>
    <SourceRevisionId>dev</SourceRevisionId>
</PropertyGroup>
```

The properties here are:

* *VersionPrefix* - leftmost part of the version,
* *VersionSuffix* - pre-release label if any,
* *SourceRevisionId* - build metadata.

The result version is `1.0.0-preview-label+dev`.

You can read more about version in .NET Core projects in **Andrew Lock**'s blog: [Version vs VersionSuffix vs PackageVersion: What do they all mean?](https://andrewlock.net/version-vs-versionsuffix-vs-packageversion-what-do-they-all-mean/).

## Semantic version validation in Adeptik

Assembly's product version must comply with [Semantic Versioning 2.0.0](https://semver.org/).

To verify this requirement, you must install the package

```console
    Install-Package Adeptik.SemanticVersion
```

In your csproj file set

```xml
<PropertyGroup>
    <VersionPrefix>1.0.0</VersionPrefix>
    <VersionSuffix>preview-label</VersionSuffix>
</PropertyGroup>
```

By default, the value of the `SourceRevisionId` property is set to `"developer.build"`.

The package validates that `Version` property is wellformed.

To disable `Version` validation you can add the following property to your csproj

```xml
<PropertyGroup>
    <ValidateSemanticVersion>false</ValidateSemanticVersion>
</PropertyGroup>
```
