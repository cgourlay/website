---
content-type: markdown
---

To run a target, use the `RunTarget` method. The `RunTarget` method should be placed at the end of the script.

	Task("Default")
	  .Does(() =>
	{
		Information("Hello World!");
	});

	RunTarget("Default");

### Passing a target to the script

All arguments passed to `Cake.exe` will also be accesible from the Cake script. You can access the arguments by using the [argument DSL](/dsl/#arguments). 

	var target = Argument("target", "Build");

	Task("Build")
	  .Does(() =>
	{
	});

	Task("Publish")
	  .IsDependentOn("Build")
	  .Does(() =>
	{
	});

	RunTarget(target);