---
title: 'Nasıl yapılır: Bir Derlemeden STL/CLR Kapsayıcısı Sunma'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
ms.openlocfilehash: ba881210f7ee48acd0e92dce3432cae92f3072ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590092"
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>Nasıl yapılır: Bir Derlemeden STL/CLR Kapsayıcısı Sunma

STL/CLR kapsayıcıları gibi `list` ve `map` şablon başvuru sınıfları uygulanır. C++ şablonları, derleme zamanında örneği oluşturulur çünkü tam olarak aynı imzaya sahip, ancak farklı derlemelerde farklı olan iki şablon sınıfları aslında farklı türleridir. Bu şablonu sınıfları bütünleştirilmiş kod sınırları arasında kullanılamaz anlamına gelir.

Çapraz derleme paylaşımı mümkün kılmak için STL/CLR kapsayıcıları yönelik genel arabirimi uygulayan <xref:System.Collections.Generic.ICollection%601>. Genel türler, C++, C# ve Visual Basic gibi destekleyen tüm diller, bu genel arabirimini kullanarak, STL/CLR kapsayıcıları erişebilirsiniz.

Bu konu adında bir C++ derlemesinde yazılmış bazı STL/CLR kapsayıcıları öğelerini görüntülemek gösterilmektedir `StlClrClassLibrary`. Erişmek için iki derleme göstereceğiz `StlClrClassLibrary`. İlk derleme, C++ ve C# ikinci yazılır.

İki derleme de C++ ile yazılmış, bir kapsayıcının yönelik genel arabirimi kullanarak erişebilirsiniz, `generic_container` typedef. Örneğin, bir kapsayıcı türü varsa `cliext::vector<int>`, genel arabirimi ise: `cliext::vector<int>::generic_container`. Benzer şekilde, bir yineleyici yönelik genel arabirimi kullanarak alabileceğiniz `generic_iterator` giriş olarak bir tür tanımı: `cliext::vector<int>::generic_iterator`.

Bu tür tanımlarından C++ üstbilgi dosyalarında bildirilen olduğundan, diğer dillerde yazılmış bunları kullanamazsınız. Bu nedenle, genel arabirimi erişmeye `cliext::vector<int>` , C# veya herhangi bir .NET dil kullanan `System.Collections.Generic.ICollection<int>`. Bu koleksiyon üzerinde yinelemek için kullanmak bir `foreach` döngü.

Aşağıdaki tabloda her bir STL/CLR kapsayıcısı uygulayan yönelik genel arabirimi listelenmektedir:

|STL/CLR kapsayıcısı|Genel arabirimi|
|------------------------|-----------------------|
|`deque<T>`|`ICollection<T>`|
|`hash_map<K, V>`|`IDictionary<K, V>`|
|`hash_multimap<K, V>`|`IDictionary<K, V>`|
|`hash_multiset<T>`|`ICollection<T>`|
|`hash_set<T>`|`ICollection<T>`|
|`list<T>`|`ICollection<T>`|
|`map<K, V>`|`IDictionary<K, V>`|
|`multimap<K, V>`|`IDictionary<K, V>`|
|`multiset<T>`|`ICollection<T>`|
|`set<T>`|`ICollection<T>`|
|`vector<T>`|`ICollection<T>`|

> [!NOTE]
> Çünkü `queue`, `priority_queue`, ve `stack` kapsayıcıları yineleyicileri desteklemez, genel arabirimler uygulayamaz ve erişilen çapraz derleme olamaz.

## <a name="example-1"></a>Örnek 1

### <a name="description"></a>Açıklama

Bu örnekte biz özel STL/CLR üye verileri içeren bir C++ sınıfı olarak bildirin. Biz, ardından sınıf özel koleksiyonlar erişim vermek için ortak yöntemleri bildirin. İki farklı şekilde, bir C++ istemciler için ve diğer .NET istemcileri için bir tane desteklemiyoruz.

### <a name="code"></a>Kod

```cpp
// StlClrClassLibrary.h
#pragma once

#include <cliext/deque>
#include <cliext/list>
#include <cliext/map>
#include <cliext/set>
#include <cliext/stack>
#include <cliext/vector>

using namespace System;
using namespace System::Collections::Generic;
using namespace cliext;

namespace StlClrClassLibrary {

    public ref class StlClrClass
    {
    public:
        StlClrClass();

        // These methods can be called by a C++ class
        // in another assembly to get access to the
        // private STL/CLR types defined below.
        deque<wchar_t>::generic_container ^GetDequeCpp();
        list<float>::generic_container ^GetListCpp();
        map<int, String ^>::generic_container ^GetMapCpp();
        set<double>::generic_container ^GetSetCpp();
        vector<int>::generic_container ^GetVectorCpp();

        // These methods can be called by a non-C++ class
        // in another assembly to get access to the
        // private STL/CLR types defined below.
        ICollection<wchar_t> ^GetDequeCs();
        ICollection<float> ^GetListCs();
        IDictionary<int, String ^> ^GetMapCs();
        ICollection<double> ^GetSetCs();
        ICollection<int> ^GetVectorCs();

    private:
        deque<wchar_t> ^aDeque;
        list<float> ^aList;
        map<int, String ^> ^aMap;
        set<double> ^aSet;
        vector<int> ^aVector;
    };
}
```

## <a name="example-2"></a>Örnek 2

### <a name="description"></a>Açıklama

Bu örnekte biz örnek 1'de bildirilen sınıf uygulayın. Bu sınıf kitaplığı kullanmak istemcileri için sırada, bildirim aracı kullanıyoruz **mt.exe** DLL bildirim dosyası eklemek için. Ayrıntılar için açıklamalarına bakın.

Bildirim aracı ve yan yana derlemeler ile ilgili daha fazla bilgi için bkz [yapı C/C++ yalıtılmış uygulamalar ve yan yana derlemeler](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).

### <a name="code"></a>Kod

```cpp
// StlClrClassLibrary.cpp
// compile with: /clr /LD /link /manifest
// post-build command: (attrib -r StlClrClassLibrary.dll & mt /manifest StlClrClassLibrary.dll.manifest /outputresource:StlClrClassLibrary.dll;#2 & attrib +r StlClrClassLibrary.dll)

#include "StlClrClassLibrary.h"

namespace StlClrClassLibrary
{
    StlClrClass::StlClrClass()
    {
        aDeque = gcnew deque<wchar_t>();
        aDeque->push_back(L'a');
        aDeque->push_back(L'b');

        aList = gcnew list<float>();
        aList->push_back(3.14159f);
        aList->push_back(2.71828f);

        aMap = gcnew map<int, String ^>();
        aMap[0] = "Hello";
        aMap[1] = "World";

        aSet = gcnew set<double>();
        aSet->insert(3.14159);
        aSet->insert(2.71828);

        aVector = gcnew vector<int>();
        aVector->push_back(10);
        aVector->push_back(20);
    }

    deque<wchar_t>::generic_container ^StlClrClass::GetDequeCpp()
    {
        return aDeque;
    }

    list<float>::generic_container ^StlClrClass::GetListCpp()
    {
        return aList;
    }

    map<int, String ^>::generic_container ^StlClrClass::GetMapCpp()
    {
        return aMap;
    }

    set<double>::generic_container ^StlClrClass::GetSetCpp()
    {
        return aSet;
    }

    vector<int>::generic_container ^StlClrClass::GetVectorCpp()
    {
        return aVector;
    }

    ICollection<wchar_t> ^StlClrClass::GetDequeCs()
    {
        return aDeque;
    }

    ICollection<float> ^StlClrClass::GetListCs()
    {
        return aList;
    }

    IDictionary<int, String ^> ^StlClrClass::GetMapCs()
    {
        return aMap;
    }

    ICollection<double> ^StlClrClass::GetSetCs()
    {
        return aSet;
    }

    ICollection<int> ^StlClrClass::GetVectorCs()
    {
        return aVector;
    }
}
```

## <a name="example-3"></a>Örnek 3

### <a name="description"></a>Açıklama

Bu örnekte, örnek 1 ve 2'de oluşturulan sınıf kitaplığı kullanan bir C++ istemci oluştururuz. Bu istemcinin kullandığı `generic_container` STL/CLR kapsayıcıları kapsayıcılar yinelemek ve bunların içeriğini görüntülemek için tür tanımları.

### <a name="code"></a>Kod

```cpp
// CppConsoleApp.cpp
// compile with: /clr /FUStlClrClassLibrary.dll

#include <cliext/deque>
#include <cliext/list>
#include <cliext/map>
#include <cliext/set>
#include <cliext/vector>

using namespace System;
using namespace StlClrClassLibrary;
using namespace cliext;

int main(array<System::String ^> ^args)
{
    StlClrClass theClass;

    Console::WriteLine("cliext::deque contents:");
    deque<wchar_t>::generic_container ^aDeque = theClass.GetDequeCpp();
    for each (wchar_t wc in aDeque)
    {
        Console::WriteLine(wc);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::list contents:");
    list<float>::generic_container ^aList = theClass.GetListCpp();
    for each (float f in aList)
    {
        Console::WriteLine(f);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::map contents:");
    map<int, String ^>::generic_container ^aMap = theClass.GetMapCpp();
    for each (map<int, String ^>::value_type rp in aMap)
    {
        Console::WriteLine("{0} {1}", rp->first, rp->second);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::set contents:");
    set<double>::generic_container ^aSet = theClass.GetSetCpp();
    for each (double d in aSet)
    {
        Console::WriteLine(d);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::vector contents:");
    vector<int>::generic_container ^aVector = theClass.GetVectorCpp();
    for each (int i in aVector)
    {
        Console::WriteLine(i);
    }
    Console::WriteLine();

    return 0;
}
```

### <a name="output"></a>Çıkış

```Output
cliext::deque contents:
a
b

cliext::list contents:
3.14159
2.71828

cliext::map contents:
0 Hello
1 World

cliext::set contents:
2.71828
3.14159

cliext::vector contents:
10
20
```

## <a name="example-4"></a>Örnek 4

### <a name="description"></a>Açıklama

Bu örnekte, örnek 1 ve 2'de oluşturulan sınıf kitaplığı kullanan bir C# istemci oluştururuz. Bu istemcinin kullandığı <xref:System.Collections.Generic.ICollection%601> STL/CLR kapsayıcıları kapsayıcılar yinelemek ve bunların içeriğini görüntülemek için yöntemleri.

### <a name="code"></a>Kod

```csharp
// CsConsoleApp.cs
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll

using System;
using System.Collections.Generic;
using StlClrClassLibrary;
using cliext;

namespace CsConsoleApp
{
    class Program
    {
        static int Main(string[] args)
        {
            StlClrClass theClass = new StlClrClass();

            Console.WriteLine("cliext::deque contents:");
            ICollection<char> iCollChar = theClass.GetDequeCs();
            foreach (char c in iCollChar)
            {
                Console.WriteLine(c);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::list contents:");
            ICollection<float> iCollFloat = theClass.GetListCs();
            foreach (float f in iCollFloat)
            {
                Console.WriteLine(f);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::map contents:");
            IDictionary<int, string> iDict = theClass.GetMapCs();
            foreach (KeyValuePair<int, string> kvp in iDict)
            {
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::set contents:");
            ICollection<double> iCollDouble = theClass.GetSetCs();
            foreach (double d in iCollDouble)
            {
                Console.WriteLine(d);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::vector contents:");
            ICollection<int> iCollInt = theClass.GetVectorCs();
            foreach (int i in iCollInt)
            {
                Console.WriteLine(i);
            }
            Console.WriteLine();

            return 0;
        }
    }
}
```

### <a name="output"></a>Çıkış

```Output
cliext::deque contents:
a
b

cliext::list contents:
3.14159
2.71828

cliext::map contents:
0 Hello
1 World

cliext::set contents:
2.71828
3.14159

cliext::vector contents:
10
20
```

## <a name="see-also"></a>Ayrıca Bkz.

[STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)