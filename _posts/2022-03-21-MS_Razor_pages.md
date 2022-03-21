---
title: (N)(L)Microsoft Razor Pages
published: true
---

## Create a web UI with ASP.NET Core

Create new project in directory

```shell
dotnet new webapp -f net6.0
```

-f fully-featured
net6.0 current version

Create new project with directory

```shell
dotnet new webapp -o *ProjectName* --no-https
```

ProjectName will be the directory name
--no-https flag specifies not to enable HTTPS.

Create page from CLI

```shell
dotnet new page --name *PAGENAME* --namespace *ProjectName.Pages* --output Pages
```

Struct:
ProjectName:

- Pages
- Model
- Service

Input Tag Helper:

```cshtml
<input asp-for="ObjectVar.Variablename" class="form-control" />
```

Model class access to model  
[BindProperty]

Built-in server-side model validation
if (!ModelState.IsValid) { return Page(); }

Attribute to indicate that a property must have a value
[Required]

Attribute to constrain a value to a specific range
[Range(x,y)]

HTTP POST page handler to the PageModel

```c#
public IActionResult OnPost() {
	if (!ModelState.IsValid) {
		return Page();
	}
	PizzaService.Add(NewPizza);
	return RedirectToAction("Get");
}
```

HTTP POST handler for delete

```html
<form method="post" asp-page-handler="Delete"></form>
```

```c#
public IActionResult OnPostDelete(int id)
{
    PizzaService.Delete(id);
    return RedirectToAction("Get");
}
```

Run project

```shell
dotnet run
```
