# Extension Methods
<h3>.net framework 4.6 , C# 6.0</h3>

###The only thing that separates this from any other static method, is the "this" keyword in the parameter section of the method. It tells the compiler that this is an extension method for the string class, and that's actually all you need to create an extension method.

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
