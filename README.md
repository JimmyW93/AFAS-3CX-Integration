# AFAS 3CX Integration

Create a GetConnector based on ```Communicatie incl. autorisatie``` and add the fields you want to use in your 3CX application and add the GetConnector to the AppConnector you want to use.

Use the column ```Contacten``` as ContactId.

Instructions on how to create an AppConnector can be found here <https://help.afas.nl/help/NL/SE/120718.htm>.

After creating the token, convert it to Base64 using the following Powershell commands:

```PowerShell
$token = "TOKEN"
$encodedToken = [System.Convert]::ToBase64String([System.Text.Encoding]::ASCII.GetBytes($token))
$encodedToken | clip
```

Paste the encoded token in the XML template. Do NOT remove the ```AfasToken``` suffix.

Modify the environment number to your own in the REST URL's.

Modify the value ```GetConnectorName``` to the name of the new GetConnector.

Modify the values in the Variables and Outputs sections to your own field names.

Example:

If you use a field named Contact instead of ContactId, ```Path="rows.ContactId"``` would be changed to ```Path="rows.Contact"```

It is also possible to use two seperate environments (or more), see `AFAS2Environments.xml`.