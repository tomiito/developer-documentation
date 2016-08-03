##Security

> Example key

```plaintext
ZZ6VkORqV25iSWOVb5cwZ03zpns
```

> Example Base URL

```plaintext
https://www.abc.com/ex.aspx?abc=def&vid=123&oenc=
```

> Example Signature

```plaintext
dYQuf4tCr1l07nDRpzO+PLSBNTQ=
```
> Example Encoded Signature

```plaintext
dYQuf4tCr1l07nDRpzO-PLSBNTQ
```

> Example Final URL

```plaintext
https://www.abc.com/ex.aspx?abc=def&vid=123&oenc=NPJPxGx_-1vHe0T1q4tt-MyWnQ4
```
Fulcrum strongly recommends taking advantage of inbound and outbound URL hashing, which will prevent respondents from manipulating links.

![SHA-1 Setup](/source/images/Supplier_sha1_flowchart_v21.png)
 
Your secret key and variable name configuration can be set or disabled in the Fulcrum UI. In order to verify the validity of any Fulcrum outbound connection or generate a hash to match with any Fulcrum inbound connection, you must create a function that computes an RFC 2014-compliant HMAC signature and substitute the following characters:

| Original | Substitute   |
|----------|--------------|
| +        | -            |
| /        | _            |
| =        | empty string |

<aside class="notice">When hashing URLs for Fulcrum your base string should include the entire URL, up to and including the `&` preceding your encryption variable.  When hashing URLs for Pulley your base string should include the entire URL up to but NOT including the `&` preceding your encryption variable.</aside>

### Generating a HMAC signature

![Supplier SHA-1](images/Supplier_sha1_flowchart_v21.png)

Accounts with Incoming SHA-1 Encryption enabled will need to generate and append an HMAC signature value when directing users to the Fulcrum domain.  For suppliers this means appending the signature to your entry links provided to Respondents.  For Buyers this means appending signatures to all Callback links on which Respondents are return to Fuclrum. For suppliers this means appending signatures on the Fulcrum entry links given to respondents. An example, of the encrypted URLs from the Supplier into Fulcrum, where the Incoming Variable Name is set to “ienc” and the Secret Key is set to 1234567890ABC. Please note that “ienc” and the secret key are merely example values.

Once an HMAC signature value has been generated, for a URL it should be added to the url following the variable name that you have set in the Fulcrum UI. Fulcrum will attempt to validate the hash once the user navigates to our platform. If Fulcrum is able to validate the signature value, the User will be allowed to proceed.  If the signature value cannot be validated the user's session will be terminated.

### Verifying a HMAC signature

> URL Without Encryption: 

```plaintext
http://www.samplicio.us/router/default.aspx?SID=12345dca-a691-4496-a2fa-12345b99ec29&PID=1234
```

> URL With Encryption: 

```plaintext
http://www.samplicio.us/router/default.aspx?SID=12345dca-a691-4496-a2fa-12345b99ec29&PID=1234&ienc=XWwaVNlMH8fxcLe5OQIh-vn5_b8
```

Accounts with Outgoing SHA-1 Encryption enabled will need to attempt to validate an HMAC signature value that Fulcrum will append when refering respondents to your platform. Buyers will see these signatures appended to the links used by Respondents to enter a client survey.  Suppliers will see these signatures appended to the links on which respondents are returned to your platform from Fulcurm.

Fulcrum will append the signature following the variable label set for the account in the Fulcrum UI.  An example of the encrypted URLs where the variable name is set to “ienc” and the Secret Key is set to 1234567890ABC. Please note that “ienc” and the secret key are merely example values.

### Configure SHA-1 Settings for an Accounts
Buyers will configure these settings by navigating to the `Clients` tab locate `{Your Account} API_Client` and click on the `Name`, you will be directed to the Client Details page where you will find the setting options under `Show Encryption`.

Suppliers will configure these settings by clicking on the `Supply` tab to navigate to the `Supplier Surveys` page.  From the supply list page click on the `Optimizer Preferences` tab, which will navigate you to the `Supplier Preferences` page, where you will select `Encryption` from the side menu.

### SHA-1 FAQ

Can I implement SHA-1 on multiple suppliers?

- Yes.In the screenshot above you can use the drop down in the top right to change encryption settings for multiple suppliers.

Do I need to use incoming and outgoing SHA-1 encryption?

- We strongly recommend implementing both incoming and outgoing encryption. Incoming encryption helps prevent URL tampering as the respondent moves further downstream to the client survey. Catching URL link tampering earlier in the process helps reduce cheating elsewhere in the Fulcrum environment which helps buyers and clients feel more confident with the quality of your panel. Outgoing encryption helps directly prevent respondents from manipulating supplier redirects in an attempt to “fake” a complete.
Where can I get help implementing incoming and outgoing SHA-1 encryption?
