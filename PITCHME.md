### State Flow
1. Interactive components (Datepicker, Customize Table, Checkboxes, etc) make changes to the URL.
2. Manager props are connected to the URL state.
3. Changes to the URL will trigger changes in the Manager components: Table, Tabs, Toolbar, etc

### API configs
* To make an API request, create an api config object. This object is passed to an Axios api client that is already configured to make requests to your platform's micro service.
* In an API config, you determine 3 things:
  * Type of request (GET, POST, etc)
  * Request URL ("twitter.hyfn.com/campaigns")
  * Params to include: ({account_id: 1, sort_by: 'objective'})

### Selectors
* Use selectors to grab data from state
* Use re-selectors to format, normalize and memoize data
* You can share selectors with each other

### URL Fetchers
* You can use URL fetchers to immediately fetch data on route changes. This is handy for making API asap if you know what you need in advance
* You can setup conditions to determine whether or not to make a request by comparing current vs previous router data.

### URL is King
* The URL is the one source of truth
* Many Manager props are connected to the URL state, through redux connect
* The table "listens" for changes to the URL, which will trigger react lifecycle methods
* You can hook into lifecycle methods to make a new api call.
