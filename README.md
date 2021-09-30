# power-apps-connector
Power Apps Connector for Exasol

This repository contains the Power Apps Connector for Exasol files.

The connector was created as follows:
- Generated a custom connector off a mock API swagger/openAPI file (v2) in the powerapps portal. Gave the actions names and IDs.
- Add the Dynamic Host Url policy to allow for different API endpoints for customers ( https://docs.microsoft.com/en-us/connectors/custom-connectors/policy-templates/dynamichosturl/dynamichosturl )
- Downloaded the connector with the paconn tool
- Added custom API endpoint parameter to apiProperties file.
- Added description to apiDefinition file (paconn would crash without it)
- The original generated connector had to be deleted since updates wouldn't be reflecting ..
- Used paconn create to reupload
- Used paconn update afterwards for more changes (working fine now)

Paconn CLI tool here (requires az tool):
https://docs.microsoft.com/en-us/connectors/custom-connectors/paconn-cli


You can set up a developer account to develop and test, free of charge, more information here:
https://go.microsoft.com/fwlink/?linkid=847282
