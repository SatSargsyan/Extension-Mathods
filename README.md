# Extension Methods
<h3>.net framework 4.6 , C# 6.0</h3>

###The only thing that separates this from any other static method, is the "this" keyword in the parameter section of the method. It tells the compiler that this is an <a href=https://msdn.microsoft.com/en-us/library/bb383977.aspx>extension method </a>for the string class, and that's actually all you need to create an extension method.

####<a href=https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp>The following list contains basic features and properties of extension methods:</a>
<ol type=1>
<li>It is a static method.
<li>It must be located in a static class.
<li>It uses the "this" keyword as the first parameter with a type in .NET and this method will be called by a given type instance on the client side.
<li>It also shown by VS intellisense. When we press the dot (.) after a type instance, then it comes in VS intellisense.
<li>An extension method should be in the same namespace as it is used or you need to import the namespace of the class by a using statement.
<li>You can give any name for the class that has an extension method but the class should be static.
<li>If you want to add new methods to a type and you don't have the source code for it, then the solution is to use and implement extension methods of that type.
<li>If you create extension methods that have the same signature methods as the type you are extending, then the extension methods will never be called.
</ol>

```C#
namespace Extension
{
    public static class ExtensionMethods
    {
        public static string UppercaseFirstLetter(this string value)
        {
            // Uppercase the first letter in the string.
            if (value.Length > 0)
            {
                char[] array = value.ToCharArray();
                array[0] = char.ToUpper(array[0]);
                return new string(array);
            }
            return value;
        }
    }

```

###We cannot write extensions for the static classes, for example math, because we cannot create new, but we can make something <a href=http://stackoverflow.com/questions/249222/can-i-add-extension-methods-to-an-existing-static-class>like this</a>.
