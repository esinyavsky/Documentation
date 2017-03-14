[Back to Home](Readme.md) 

# Release Notes - Content API V3

- [API Codes and Error Messages](#api-codes-and-error-messages)
- [Use Codes](#use-codes)

## API Codes and Error Messages
### JSON Error Messages

**_Important note for users of JSON search results:_** If you are currently requesting search results in JSON, you must _make changes to your client application_ to process the error messages returned in JSON.

By default, error messages are returned in XML. If JSON is requested (in the _Accept_ header or in the format parameter value), the error is now returned in JSON. For example, the following error is returned if JSON is requested and _detail=tires_ is specified instead of _detail=tiers_ in the My Plans request:

```JSON
{
  "code": 400,
  "detailCode": 5001,
  "message": "Specified value for detail 'tires' is invalid"
}
```
### Detail Error Codes

In addition to HTTP status codes, Content API now returns detail error codes if available. For example, the following error is returned if _query_ is specified instead of _q_ in the search request:

```XML
<Error xmlns:i="http://www.w3.org/2001/XMLSchema-instance"> 
   <Code>400</code> 
   <DetailCode>5000</DetailCode> 
   <Message>Specified parameter 'query' is invalid</Message>
</Error>
```

**To access the list of detail error codes in XML:**

    http://api.ap.org/v2/docs/errors?apikey={apiKey}

**To access the list of detail error codes in JSON:**

    http://api.ap.org/v2/docs/errors?apikey={apiKey}&format=json

For more information about API codes and suggested actions, see "API Codes".

[Back to Top](#release-notes---content-api-v3) 

## Use Codes

### Search Results and Full Item Metadata

A use code is now returned in addition to the pricing message in search results and full item metadata responses if the _showPricing=true_ parameter is specified in the request:

| Pricing Scenario | Use Code | Plan Type | API Pricing Message
| --- | --- | --- |--- |
| Included in Your Plan | 810 | Choice | Included in your Choice plan at the Tier indicated
| Included in Your Plan | 801 | Other plans| Included in your plan
| Not Included in Your Plan (Extra Charge) | 851 | All plans| Not included in your plan. Available for an extra charge.
| Not Included in Your Plan (Contact Licensing) | 860 | All plans| Not included in your plan. To learn more about license rights, please contact your licensing representative.

#### XML

In XML search results and full item metadata responses, the use code for the pricing message is returned in the "role" attribute of the `usageTerms `element (for example, `role="apusecode:801"`):

```XML
<usageTerms role="apusecode:801">Included in your plan.</usageTerms>
```

####JSON

In JSON search results, the pricing message use code is returned in the "apUseCode" property; for example:

```JSON
"usageTerms": [
   "This content is intended for editorial use only. For other uses, additional clearances may be required.",
   "No Use in Japan",
   "Included in your plan."],
"apUseCode": "801",
```

[Back to Top](#release-notes---content-api-v3) 