# Security in ASP.NET Core

TODO : Move to cheat_aspnetcore.md


>> WARNING : This code is not production ready

## Test if user is authorized

``` c#
// Verifies only if the default policy applies to the user
public static async Task<bool> IsUserAuthorizedAsync(this HttpContext context, string? scheme = null, string? policyName = null)
{
    var authenticationService = context.RequestServices.GetRequiredService<IAuthenticationService>();
    var authenticateResult = await authenticationService.AuthenticateAsync(context, scheme);
    if (!authenticateResult.Succeeded)
    {
        return false;
    }

    var policyProvider = context.RequestServices.GetRequiredService<IAuthorizationPolicyProvider>();
    var authorizationService = context.RequestServices.GetRequiredService<IAuthorizationService>();
    var policy = policyName == null
        ? await policyProvider.GetDefaultPolicyAsync()
        : await policyProvider.GetPolicyAsync(policyName);
    if (policy == null)
    {
        throw new InvalidOperationException($"The '{policyName ?? "default"}' policy is unknown.");
    }
    var result = await authorizationService.AuthorizeAsync(context.User, null, policy);
    return result.Succeeded;
}
```

## Get cookie name

``` c#
public static string? GetCookieName(this HttpContext context, string? scheme = null)
{
    var options = context.RequestServices.GetRequiredService<IOptionsMonitor<CookieAuthenticationOptions>>();
    var cookieOptions = options.Get(scheme);
    return cookieOptions?.Cookie.Name;
}


HttpContext context = /* .. */;
var name = context.GetCookieName(IdentityConstants.ApplicationScheme); // default when using ConfigureApplicationCookie()
Assert.AreEquals("AspNetCore.Identity.Application", name);  // Note: Different when environment <> ('Development' || 'Production')


```



