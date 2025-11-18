# Cheat Sheet - C# Libraries


## Base64

``` c#
// Base64
using System;
Assert.AreEqual("SGVsbG8=", Convert.ToBase64String(Encoding.UTF8.GetBytes("Hello")));
Assert.AreEqual("Hello", Encoding.UTF8.GetString(Convert.FromBase64String("SGVsbG8=")));

// Base64-URL + UTF8
using Microsoft.IdentityModel.Tokens;
Assert.AreEqual("SGVsbG8", Base64UrlEncoder.Encode("Hello"));
Assert.AreEqual("Hello", Base64UrlEncoder.Decode("SGVsbG8"));
```


## JSON

``` c#
using Newtonsoft.Json;
Assert.AreEqual(null, JsonConvert.DeserializeObject<Test>(""));
Assert.AreEqual(null, JsonConvert.DeserializeObject<Test>("null"));
Assert.Throws<JsonReaderException>(() => JsonConvert.DeserializeObject<Test>("<html>"));
```
