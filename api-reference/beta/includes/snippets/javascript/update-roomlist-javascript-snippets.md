---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const place = {
  @odata.type: "microsoft.graph.roomlist",
  displayName: "Building 1",
  phone:"555-555-0100"
};

let res = await client.api('/places/Building1RroomList@contoso.onmicrosoft.com')
	.version('beta')
	.update(place);

```