ASP.Net MVC Razor Display and Editor Templates
==============================================

Introduction
------------

Razor view implementations of the built-in templates used by the Display / DisplayFor and Editor / EditorFor HtmlHelper extension methods.

This solution is based on ASP.Net MVC Framework version 4, but could probably be adapted to an earlier version.


Razor Templates for Display / DisplayFor and Editor / EditorFor
---------------------------------------------------------------
By default, the markup output by HtmlHelper's Display / DisplayFor and Editor / EditorFor methods is generated internally by the framework. 

It is possible to override the default markup by adding appropriately named partial views to the following folders within your ASP.Net MVC application

~/Views/Shared/DisplayTemplates
~/Views/Shared/EditorTemplates

This project provides Razor alternatives for all of the built-in logic used by Display and Editor extension methods. They generate the default markup and provide a useful starting point for developers wanting to introduce changes specific to their application.

Some examples of things you can do once you have the templates in place:

- Change markup, e.g. add css classes to input elements, use graphics / words for displaying boolean values etc.
- Introduce parameterised variations using additionalViewData parameter, e.g. @Html.Editor("Name", new { level = "warning" })
- Change surrounding HTML generated by Html.DisplayForModel to support your project's CSS layout framework

The templates are based on the logic within the following classes in the ASP.Net MVC Framework:

- [DefaultDisplayTemplates.cs](https://github.com/ASP-NET-MVC/aspnetwebstack/blob/master/src/System.Web.Mvc/Html/DefaultDisplayTemplates.cs)
- [DefaultEditorTemplates.cs](https://github.com/ASP-NET-MVC/aspnetwebstack/blob/master/src/System.Web.Mvc/Html/DefaultEditorTemplates.cs)

Note that the MVC4 editors support new HTML5 input elements.


New HtmlHelper Extension Methods: EditorSection / EditorSectionFor and DisplaySection / DisplaySectionFor
---------------------------------------------------------------------------------------------------------
 
In addition to the standard Razor templates, some new extension methods have been added to support the display of values with surrounding HTML, labels and validation elements. See DisplayExtensions and EditorExtensions - details to be documented soon.


How to Use
----------
Copy the following directories to the views folder of your ASP.Net MVC web application project:

src\DemoMvcApp\Views\Shared\DisplayTemplates
src\DemoMvcApp\Views\Shared\EditorTemplates

You'll need to either clone this repository or download the files in the [DisplayTemplates](https://github.com/danmalcolm/mvc-razor-display-and-editor-templates/src/DemoMvcApp/Views/Shared/DisplayTemplates) and [EditorTemplates] (https://github.com/danmalcolm/mvc-razor-display-and-editor-templates/src/DemoMvcApp/Views/Shared/DisplayTemplates) folders.

The framework will now use these templates, instead of rendering edit / display markup using the built-in templates.

Edit the .cshtml files to change the markup and add functionality. 

A NuGet package will be added once I've done a bit more testing.

Development
-----------
If you want to experiment / play around:

- Clone the repository or [download the solution]() from Github if you're not familiar with git
- Open the solution in Visual Studio
- Set DemoMvcApp as your startup project and hit F5.

The solution is compatible with Visual Studio 2012 only.


To Do
-----
Put demo site on AppHarbor / Azure

Separate sites:

- StandardTemplates - just templates, nothing else
- EditorExtensions - templates + DisplaySection / EditorSection functionality
- Twitter Bootstrap - example of customising templates to simplify form generation etc