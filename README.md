# SFDX  App

# Help Sample Commands

Mainly as a record of the needed commands

```
cat sfdx-test-project/.git/config
rm -rf sfdx-test-project
git clone https://github.com/luik/sfdx-test-project.git
cd sfdx-test-project
sfdx force:org:list
sfdx force:config:set defaultdevhubusername=lyucra@devhub.com
sfdx force:org:create -f config/project-scratch-def.json 
sfdx force:org:list
sfdx force:config:set defaultusername=test-uulzrhmarbhx@example.com
sfdx force:data:tree:import -f data/Case.json
sfdx force:org:open

---------------------------------------------------------------------------------

sfdx force:data:soql:query --query "Select Origin, Subject, Description From Case"
sfdx force:data:tree:export --query "Select Origin, Subject, Description From Case" -d data

----------------------------------------------------------------------------------

sfdx force:org:delete --targetusername test-uulzrhmarbhx@example.com

----------------------------------------------------------------------------------

sfdx force:package:install --package 04t0H000001Dy1g

-------------------------------------------------------------------------------

sfdx force:user:password:generate

-------------------------------------------------------------------------------



sfdx force:user:display
```

## Open setup page
sfdx force:org:open -p /lightning/setup



## Confluence Notes

To get Articles in Draft status

`SELECT Id, Title, Body__c FROM Knowledge__kav WHERE PublishStatus='Draft'`

`sfdx force:data:soql:query --query "SELECT Id, Title, UrlName, Body__c FROM Knowledge__kav WHERE PublishStatus='Draft'"` 

`sfdx force:data:tree:export --query "SELECT Title, UrlName, Body__c FROM Knowledge__kav WHERE PublishStatus='Draft'" -d data` 

`sfdx force:data:tree:import -f data/Knowledge__kav.json`

`delete [SELECT Id FROM Knowledge__kav WHERE Id='ka00v0000005DI3AAM'];`

```
Knowledge__kav item = [SELECT Id, Body__c FROM Knowledge__kav WHERE Id='ka00v0000005DI8AAM'];
item.Body__c = '<div>body1</div>';

update item;
```



```
Knowledge__kav item = [SELECT Id, Body__c FROM Knowledge__kav WHERE Id='ka00v0000005DcRAAU'];
item.Body__c = '<div>body2</div>';

update item;
```

