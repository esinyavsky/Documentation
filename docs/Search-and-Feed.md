[Back to Home](Readme.md) 

# Search and Feed
- [Search Method](#search-method)
- [Feed Method](#feed-method)
- [Supported Query Syntax](#supported-query-syntax)

## Search Method

### Description
Searches content using the specified search criteria. Optionally, returns content item pricing information.

### Request
- Method: _GET_
- Request URI:
```
https://api.ap.org/[{version}]/content/search?api_key={api_key}[{optional_parameters}]
```
> **_Important:_** The request URI must be URL-encoded.

#### Base URI Parameter
- **version** (optional): The API version; for example, _v2_. When this parameter value is not specified, the latest API version is returned. 

#### Optional Parameters
> **_Note_**: An implied AND operator is used between the parameters.

- **q**: The query expression used to search for content. For more information, see [Supported Query Syntax](#supported-query-syntax).

- **include**: A comma-separated list of fields to include in the response.

- **exclude**: A comma-separated list of fields to exclude from the response.

- **view**: Returns a predefined set of fields for each content item:
  - _basic_: A limited set of fields (this is the default).
  - _full_: All available fields.

- **content_set**: The content set to be searched. For the AP Images content, valid options are:
  - _editorial_: Editorial images.
  - _creativeRM_: Creative rights-managed images.
  - _creativeRF_: Creative royalty-free images.
  - _GraphicsBank_: All GraphicsBank content.
  - _GraphicsBank_Graphic_: Graphics content from GraphicsBank.
  - _GraphicsBank_Photo_: Photo content from GraphicsBank.
  - _all_: All available content sets (this is the default).
  
- **pricing**. By default, pricing information is not returned in the response. When *pricing=true* is specified in the request, the response includes pricing for each content item.

- **all_filings**. When *all_filings=true* is specified in the request, the response includes all filings of ANPA and/or IPTC-formatted stories. If this parameter is not used, only the latest filing of a story is returned.

- **page**: The requested page number within the set of search results. The default is 1. 

- **page_size**: The maximum number of results to return per page. The default is 25 results with a maximum of 100 per page.

- **sort**: The sort order of the returned results.

- **parametrics**: By default, query facets that allow you to refine the original search are returned for each content item at the entry level only. When *parametrics=true* is specified in the request, the response also includes query facets for the entire result set in the "queries" array at the top of the JSON response. 

- **format**: The response format (currently, the only valid value is *json*). If no format is specified as the *format* parameter value or in the Accept header, JSON is returned. The *format* parameter value takes precedence over the Accept header value when both are specified.

#### Request Headers (Optional)

- **Accept**: The MIME type of the returned data format (currently, only JSON is supported). The default is *application/json*. The format parameter value takes precedence over the Accept header value when both are specified.

- **Accept-Encoding**: Compresses the response to the gzip format. The valid value is *gzip*.

[Back to Top](#search-and-feed) 

## Feed Method

### Description
Returns a feed of content matching the specified criteria. Optionally, returns content item pricing information.

### Request
- Method: _GET_
- Request URI:
```
https://api.ap.org/[{version}]/content/feed?api_key={api_key}[{optional_parameters}]
```
> **_Important:_** The request URI must be URL-encoded.

#### Base Request URI Parameter
- **version** (optional): The API version; for example, _v2_. When this parameter value is not specified, the latest API version is returned. 

#### Optional Parameters
> **_Note_**: An implied AND operator is used between the parameters.

- **q**: The query expression used to filter content. For more information, see [Supported Query Syntax](#supported-query-syntax).

- **include**: A comma-separated list of fields to include in the response.

- **exclude**: A comma-separated list of fields to exclude from the response.

- **view**: Returns a predefined set of fields for each content item:
  - _basic_: A limited set of fields (this is the default).
  - _full_: All available fields.

- **content_set**: The content set to be searched. For the AP Images content, valid options are:
  - _editorial_: Editorial images.
  - _creativeRM_: Creative rights-managed images.
  - _creativeRF_: Creative royalty-free images.
  - _GraphicsBank_: All GraphicsBank content.
  - _GraphicsBank_Graphic_: Graphics content from GraphicsBank.
  - _GraphicsBank_Photo_: Photo content from GraphicsBank.
  - _all_: All available content sets (this is the default).
  
- **pricing**. By default, pricing information is not returned in the response. When *pricing=true* is specified in the request, the response includes pricing for each content item.

- **all_filings**. When *all_filings=true* is specified in the request, the response includes all filings of ANPA and/or IPTC-formatted stories. If this parameter is not used, only the latest filing of a story is returned.

- **page**: The requested page number within the set of search results. The default is 1. 

- **page_size**: The maximum number of results to return per page. The default is 25 results with a maximum of 100 per page.

- **format**: The response format (currently, the only valid value is *json*). If no format is specified as the *format* parameter value or in the Accept header, JSON is returned. The *format* parameter value takes precedence over the Accept header value when both are specified.

#### Request Headers (Optional)

- **Accept**: The MIME type of the returned data format (currently, only JSON is supported). The default is *application/json*. The format parameter value takes precedence over the Accept header value when both are specified.

- **Accept-Encoding**: Compresses the response to the gzip format. The valid value is *gzip*.

[Back to Top](#search-and-feed) 

## Supported Query Syntax

[Back to Top](#search-and-feed) 

