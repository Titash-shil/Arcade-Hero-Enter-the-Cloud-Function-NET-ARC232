# Arcade Hero: Enter the Cloud Function NET || [ARC232](https://www.cloudskillsboost.google/focuses/98841?catalog_rank=%7B%22rank%22%3A1%2C%22num_filters%22%3A0%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=34929923) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

### Run the following Commands in CloudShell

```
export REGION=
```
```
gcloud config set compute/region $REGION
export PROJECT_ID=$(gcloud config get-value project)


mkdir quicklab && cd quicklab


cat > Function.cs <<'EOF_END'
using Google.Cloud.Functions.Framework;
using Microsoft.AspNetCore.Http;
using System.Threading.Tasks;

namespace HelloWorld;

public class Function : IHttpFunction
{
    public async Task HandleAsync(HttpContext context)
    {
        await context.Response.WriteAsync("Hello World!", context.RequestAborted);
    }
}
EOF_END

cat > HelloHttp.csproj <<'EOF_END'
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net6.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Google.Cloud.Functions.Hosting" Version="2.2.1" />
  </ItemGroup>
</Project>
EOF_END

#HelloHttp.Function entery point


  gcloud functions deploy cf-demo \
    --gen2 \
    --entry-point=HelloWorld.Function \
    --runtime=dotnet6 \
    --region=$REGION \
    --source=. \
    --trigger-http \
    --allow-unauthenticated \
    --quiet
```

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
