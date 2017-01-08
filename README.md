# ErrorUnit.Injector_WebApi
Documentation on using ErrorUnit Web Api ActionFilter to instrument calls

To catch Web API Errors add to `GlobalConfiguration.Configure(WebApiConfig.Register)` method that is called by Global.asax.cs Application_Start method the code:
```
config.Filters.Add(new ErrorUnit.Attributes.ErrorUnitWebApiActionFilterAttribute());
```
## Examples
So the full code for the WebApiConfig class in you App_Start folder should look like:
```
using System.Web.Http;

public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        config.Filters.Add(new ErrorUnit.Attributes.ErrorUnitWebApiActionFilterAttribute());
        //Web API routes ...
    }
}
```
