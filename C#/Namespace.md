# Namespace
C# 에서는 다른 파일의 코드를 `export, import` 할 때 `namespace, using`을 사용

``` cs
// SomeClass.cs
namespace SomeClass
{
    class Something
    {
        ...;
    }
}
```
``` cs
// MainClass.cs
using SomeClass;

class Program
{
    public static void Main(string[] args)
    {
        SomeClass.Something t1 = new SomeClass.Something();
    }
}
```