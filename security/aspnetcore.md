# Security in ASP.NET Core

>> WARNING : This code is not production ready

## Test if user is authorized

``` c#
// Verifies only if the default policy applies to the user
public static async Task<bool> IsUserAuthorizedAsync(this HttpContext context)
{
    var authorizationPolicy = context.RequestServices.GetRequiredService<IAuthorizationService>();
    var policyProvider = context.RequestServices.GetRequiredService<IAuthorizationPolicyProvider>();

    var defaultPolicy = await policyProvider.GetDefaultPolicyAsync();
    var result = await authorizationPolicy.AuthorizeAsync(context.User, null, defaultPolicy);
    return result.Succeeded;
}
```
