---
title: "AppSourceCop Analyzer"
ms.author: solsen
ms.custom: na
ms.date: 10/15/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: solsen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# AppSourceCop Analyzer Rules
AppSourceCop is an analyzer that enforces rules that must be respected by extensions meant to be published to Microsoft AppSource.

## Rules

|Id|Title|Description|MessageFormat|Category|Default Severity|IsEnabledbyDefault|
|--|-----|-----------|-------------|--------|----------------|------------------|
|[AS0001](appsourcecop-as0001-tabledeletionnotallowed.md)|Tables and table extensions that have been published should not be deleted, since dependent extensions may break.|Tables and table extensions that have been published should not be deleted.|'{0}' has been deleted.|Upgrade|Error|true|
|[AS0002](appsourcecop-as0002-fielddeletionnotallowed.md)|Fields should not be deleted, since dependent extensions may break.|Fields should not be deleted.|Field '{0}' has been deleted from table '{1}'.|Upgrade|Error|true|
|[AS0003](appsourcecop-as0003-previousversionnotfound.md)|The previous version was not found.|The previous version was not found.|The previous version was not found. Name='{0}', Publisher='{1}', Version'{2}'.|Upgrade|Warning|true|
|[AS0004](appsourcecop-as0004-fieldtypechangenotallowed.md)|Fields should not change type, since dependent extensions may break.|Fields should not change type.|Field '{0}' has changed type from '{1}' to '{2}'. Type changes are not allowed.|Upgrade|Error|true|
|[AS0005](appsourcecop-as0005-fieldnamechangenotallowed.md)|Fields should not change name, since dependent extensions may break.|Fields should not change name.|Field '{0}' has changed name to '{1}'. Name changes are not allowed.|Upgrade|Error|true|
|[AS0006](appsourcecop-as0006-tablenamechangenotallowed.md)|Tables and table extensions that have been published should not change name, since dependent extensions may break.|Tables and table extensions that have been published should not change name.|Object '{0}' has changed name to '{1}'. Name changes are not allowed.|Upgrade|Error|true|
|[AS0007](appsourcecop-as0007-propertyvaluechangenotallowed.md)|Properties should not change value, since dependent extensions may break.|Properties should not change value.|The property '{0}' has changed value. Value change is not allowed for this property.|Upgrade|Error|true|
|[AS0009](appsourcecop-as0009-keyfieldschangenotallowed.md)|Key fields should not be changed.|Key fields should not be changed.|Key '{0}' has changed the key fields. Changes to the field list are not allowed.|Upgrade|Error|true|
|[AS0010](appsourcecop-as0010-primarykeydeletenotallowed.md)|Keys should not be deleted, since dependent extensions may break.|The primary key must not be deleted.|Key '{0}' has been deleted. The primary key may not be deleted.|Upgrade|Error|true|
|[AS0011](appsourcecop-as0011-identifiersmusthaveaffix.md)|An affix is required.|An affix is required.|The identifier '{0}' must have at least one of the mandatory affixes '{1}'.|Extensibility|Error|true|
|[AS0013](appsourcecop-as0013-fieldidmustbewithinallocatedrange.md)|The field identifier must be within the allowed range.|The field identifier must be within the allowed range.|The field identifier '{0}' is not valid. It must be within the allowed range {1}.|Extensibility|Error|true|
|[AS0014](appsourcecop-as0014-projectmanifestmustspecifyidrange.md)|The project manifest must contain the allocated identifier range.|The project manifest must contain the allocated identifier range.|The project manifest must contain the allocated identifier range.|Extensibility|Error|true|
|[AS0015](appsourcecop-as0015-translationsmustbeenabled.md)|Please enable the TranslationFile feature in the app.json file for your project.|Please enable the TranslationFile feature in the app.json file for your project.|Please enable the TranslationFile feature in the app.json file for your project.|Extensibility|Error|true|
|[AS0016](appsourcecop-as0016-dataclassificationmustbespecified.md)|Fields of field class 'Normal' must use the DataClassification property and its value should be different from ToBeClassified.|Fields of field class 'Normal' must use the DataClassification property and its value must be different from ToBeClassified. FlowFields and FlowFilter fields are automatically set to the SystemMetadata data classification.|Field with name '{0}' must use the DataClassification property and its value should be different from ToBeClassified.|Extensibility|Error|true|
|[AS0018](appsourcecop-as0018-publicapiprocedureremovalnotallowed.md)|A procedure belonging to a public API cannot be modified.|A procedure belonging to a public API cannot be modified.|Procedure '{0}' has been modified in '{1} {2}'. A procedure belonging to a public API should not be removed.|Upgrade|Error|true|
|[AS0019](appsourcecop-as0019-eventattributecannotberemoved.md)|Event attributes cannot be removed.|Removing Event attributes such as IntegrationEvent or BusinessEvent is not allowed.|An IntegrationEvent/BusinessEvent attribute has been removed from '{0}'.|Upgrade|Error|true|
|[AS0020](appsourcecop-as0020-businesseventattributecannotberemoved.md)|A BusinessEvent attribute cannot be removed.|A BusinessEevent attribute cannot be removed.|A BusinessEvent attribute has been removed from '{0}'.|Upgrade|Error|true|
|[AS0021](appsourcecop-as0021-argumentineventattributecannotbechangedtofalse.md)|An Argument in an event attribute cannot be changed to false.|An Argument in an event attribute cannot be changed to false.|An Argument in an event attribute for procedure '{0}' should not be changed to false.|Upgrade|Error|true|
|[AS0022](appsourcecop-as0022-externalscopecannotberemoved.md)|An External scope cannot be removed.|An External scope cannot be removed.|The External scope in '{0}' cannot be removed or changed to 'internal'. Note that adding 'local' overrides the argument in 'Scope'.|Upgrade|Error|true|
|[AS0023](appsourcecop-as0023-returntypecannotbemodifiedinpublicapi.md)|A return type cannot be modified in events and external procedures.|A return type cannot be modified in events and external procedures.|The return type in '{0}' should not be modified.|Upgrade|Error|true|
|[AS0024](appsourcecop-as0024-parameterscannotberemovedoraddedinexternalprocedures.md)|Parameters cannot be removed or added in external procedures.|Parameters cannot be removed or added in external procedures.|Parameters have been removed or added in '{0}', this should be avoided in external procedures.|Upgrade|Error|true|
|[AS0025](appsourcecop-as0025-parameterscannotberemovedfromevents.md)|Parameters cannot be removed from events.|Parameters cannot be removed from events.|Parameters have been removed from '{0}', this should be avoided in events.|Upgrade|Error|true|
|[AS0026](appsourcecop-as0026-parametertypesubtypecannotbemodifiedinpublicapi.md)|Parameters type and subtype cannot be modified in events and external procedures.|Parameters type and subtype cannot be modified in events and external procedures.|Parameters type or subtype has been modified in '{0}', this should be avoided in events and external procedures.|Upgrade|Error|true|
|[AS0027](appsourcecop-as0027-modifyingarraysizeofvarparameterinpublicapi.md)|Modifying the array size of a var parameter in events and external procedures is not allowed.|Modifying the array size of a var parameter in events and external procedures is not allowed.|The array size of a var parameter in '{0}' has been modified, this should be avoided in events and external procedures.|Upgrade|Error|true|
|[AS0028](appsourcecop-as0028-reducingarraysizeofparameterinpublicapi.md)|Reducing the array size of a parameter in events and external procedures is not allowed.|Reducing the array size of a parameter in events and external procedures is not allowed.|The array size of a parameter in '{0}' has been reduced, this should be avoided in events and external procedures.|Upgrade|Error|true|
|[AS0029](appsourcecop-as0029-pagedeletionnotallowed.md)|Pages and PageExtensions that have been published should not be deleted, since dependent extensions may break.|Pages and PageExtensions that have been published should not be deleted.|{0} '{1}' has been deleted.|Upgrade|Error|true|
|[AS0030](appsourcecop-as0030-pagerenamenotallowed.md)|Pages and PageExtensions that have been published should not be renamed, since dependent extensions may break.|Pages and PageExtensions that have been published should not be renamed.|{0} '{1}' has been renamed to '{3}'.|Upgrade|Error|true|
|[AS0031](appsourcecop-as0031-actiondeletionnotallowed.md)|Actions that have been published should not be deleted, since dependent extensions may break.|Actions that have been published should not be deleted.|Action '{0}' on page '{1}' has been deleted.|Upgrade|Error|true|
|[AS0032](appsourcecop-as0032-controldeletionnotallowed.md)|Controls that have been published should not be deleted, since dependent extensions may break.|Controls that have been published should not be deleted.|Control '{0}' on page '{1}' has been deleted.|Upgrade|Error|true|
|[AS0033](appsourcecop-as0033-viewdeletionnotallowed.md)|View that have been published should not be deleted, since dependent extensions may break.|View that have been published should not be deleted.|View '{0}' on page '{1}' has been deleted.|Upgrade|Error|true|
|[AS0034](appsourcecop-as0034-destructivetablepropertychangenotallowed.md)|Property changes that cause destructive changes are not allowed.|Destructive table properties that have been published should not be modified.|Property '{0}' has changed value from '{1}' to '{2}', this is a destructive change.|Upgrade|Error|true|
|[AS0036](appsourcecop-as0036-destructivetablefieldpropertychangenotallowed.md)|Property changes that cause destructive changes are not allowed.|Destructive field properties that have been published should not be modified.|Property '{0}' has changed value from '{1}' to '{2}', this is a destructive change.|Upgrade|Error|true|
|[AS0038](appsourcecop-as0038-destructivekeypropertychangenotallowed.md)|Property changes that cause destructive changes are not allowed.|Destructive key properties that have been published should not be modified.|Property '{0}' has changed value from '{1}' to '{2}', this is a destructive change.|Upgrade|Error|true|
|[AS0039](appsourcecop-as0039-destructivetablepropertyremovenotallowed.md)|Removing properties that cause destructive changes are not allowed.|Destructive table properties that have been published should not be removed.|Property '{0}' has been removed, this is a destructive change.|Upgrade|Error|true|
|[AS0041](appsourcecop-as0041-destructivetablefieldpropertyremovenotallowed.md)|Table field property changes that cause destructive changes should not be removed.|Table field property changes that cause destructive changes should not be removed.|Property '{0}' has been removed, this is a destructive change.|Upgrade|Error|true|
|[AS0042](appsourcecop-as0042-destructivekeypropertyremovenotallowed.md)|Table key property changes that cause destructive changes should not be removed.|Table key property changes that cause destructive changes should not be removed.|Property '{0}' has been removed, this is a destructive change.|Upgrade|Error|true|
|[AS0043](appsourcecop-as0043-uniquekeydeletenotallowed.md)|Unique keys should not be deleted.|Unique keys should not be deleted.|Key '{0}' has been deleted. Unique key deletions are not allowed.|Upgrade|Error|true|
|[AS0044](appsourcecop-as0044-destructivetablefieldpropertyoptionmemberschangenotallowed.md)|Property changes that cause destructive changes are not allowed.|Destructive field properties that have been published should not be modified.|OptionMembers has changed value from '{0}' to '{1}', this is a destructive change, only appending new OptionMembers is allowed.|Upgrade|Error|true|
|[AS0045](appsourcecop-as0045-permissionsmustbeassigned.md)|Permissions for the object are missing.|Permissions for the object are missing.|No permissions for object {0} {1} found in database.|Permissions|Warning|true|
|[AS0046](appsourcecop-as0046-correctpermissionsmustbeassigned.md)|The assigned permissions are not correct.|The assigned permissions are not correct.|Missing {0} {1} permission for Role ID {2} for object {3} {4}.|Permissions|Warning|true|
|[AS0047](appsourcecop-as0047-extensionnamelengthmustnotexceedlimit.md)|The extension name length must not exceed the specified limit.|The extension name length must not exceed the specified limit.|The length of the extension name must not exceed {0} characters.|Extensibility|Error|true|
|[AS0048](appsourcecop-as0048-extensionpublisherlengthmustnotexceedlimit.md)|The extension publisher length must not exceed the specified limit.|The extension publisher length must not exceed the specified limit.|The length of the extension publisher must not exceed {0} characters.|Extensibility|Error|true|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)

> [!NOTE]  
> Several rules enforced by the AppSourceCop analyzer are incompatible with rules enforced by the PerTenantExtensionCop. Make sure to enable only one of these at a time.

## Configuration
The AppSourceCop analyzer can be further configured by adding a file named ```AppSourceCop.json``` in the project's root folder. The AL Language extension will offer intellisense for this file.

The following table describes the settings in the ```AppSourceCop.json``` file:

|Setting|Mandatory|Value|
|-------|---------|-----|
|name|No|The name of a previous version of this package with which you want to compare the current package for breaking changes.|
|publisher|No|The publisher of a previous version of this package with which you want to compare the current package for breaking changes.|
|version|Yes|The version of a previous version of this package with which you want to compare the current package for breaking changes.|
|mandatoryAffixes|No|Affixes that must be prepended or appended to the name of all new application objects, extension objects, and fields.|

The ```name```, ```publisher```, ```version``` properties are used for specifying a previous version of the current package. AppSourceCop will use this information to download the specified package from the server and compare the current package with it. AppSourceCop will report any breaking changes introduced by the current package.

The ```mandatoryAffixes``` property specifies strings that must be prepended or appended to the names of all new objects, extension objects and fields. By using these affixes, you can prevent clashes between objects added by your extension and objects added by other extensions.

## Example
In the following example, we will configure AppSourceCop to validate that all new elements have a name that contains one of the specified affixes.

> [!NOTE]  
> Make sure code analysis is enabled and ```${AppSourceCop}``` is in the list of enabled code analyzers.

We start by creating the default "Hello world" extension.
```
pageextension 50100 CustomerListExt extends "Customer List"
{
    trigger OnOpenPage();
    begin
        begin
            Message('App published: Hello world');
        end;
    end;
}
```

We continue by adding the configuration file ```AppSourceCop.json``` in the project's root folder and setting its content to the following. 

```
{
    "mandatoryAffixes": [ "Foo", "Bar" ]
}
```

You are immediately greeted by the following error message:
```
AS0011: The identifier 'CustomerListExt' must have at least one of the mandatory affixes 'Foo, Bar'.
```

Prepending **Foo** to the name of the page extension object will fix this error and prevent clashes between this page extension and page extensions added by other developers.

> [!NOTE]  
> It is still possible to use the ```mandatoryPrefix``` and ```mandatorySuffix``` properties in the ```AppSourceCop.json```, for more information see [AS0011](appsourcecop-as0011-identifiersmusthaveaffix.md).

## See Also  
[Using the Code Analysis Tool](../devenv-using-code-analysis-tool.md)  
[Ruleset for the Code Analysis Tool](../devenv-rule-set-syntax-for-code-analysis-tools.md)  
[Using the Code Analysis Tools with the Ruleset](../devenv-using-code-analysis-tool-with-rule-set.md)  