# CREATE DATASHARE<a name="r_CREATE_DATASHARE"></a>

Creates a new datashare in the current database\. The owner of this datashare is the issuer of the CREATE DATASHARE command\.

Amazon Redshift associates each datashare with a single Amazon Redshift database\. Superusers and database owners can create datashares\. You can only add objects from the associated database to a datashare\. You can create multiple datashares on the same Amazon Redshift database\.

To view information about the datashares, use [SHOW DATASHARES](r_SHOW_DATASHARES.md)\.

## Syntax<a name="r_CREATE_DATASHARE-synopsis"></a>

```
CREATE DATASHARE datashare_name
[[SET] PUBLICACCESSIBLE [=] TRUE | FALSE ];
```

## Parameters<a name="r_CREATE_DATASHARE-parameters"></a>

*datashare\_name*  
The name of the datashare\. The datashare name must be unique in the cluster namespace\.

\[\[SET\] PUBLICACCESSIBLE\]  
A clause that specifies whether the datashare can be shared to clusters that are publicly accessible\.  
The default value for `SET PUBLICACCESSIBLE` is `FALSE`\.

## Usage notes<a name="r_CREATE_DATASHARE_usage"></a>

By default, the owner of the datashare only owns the share but not objects within the share\.

Only superusers and the database owner can use CREATE DATASHARE and delegate ALTER privileges to other users or groups\. 

## Examples<a name="r_CREATE_DATASHARE_examples"></a>

The following example creates the datashare SalesShare\.

```
create datashare SalesShare;
```