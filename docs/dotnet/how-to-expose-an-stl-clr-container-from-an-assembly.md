---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: bir derlemeden STL/CLR kapsayıcısını kullanıma sunma'
title: 'Nasıl yapılır: Bir Derlemeden STL/CLR Kapsayıcısı Sunma'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
ms.openlocfilehash: a4ed92af956def030c80f8f303f0a7501c4944c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134985"
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>Nasıl yapılır: Bir Derlemeden STL/CLR Kapsayıcısı Sunma

Ve gibi STL/CLR kapsayıcıları `list` `map` şablon başvuru sınıfları olarak uygulanır. C++ şablonları derleme zamanında örneklendiği için, tam olarak aynı imzaya sahip ancak farklı derlemelerdeki iki şablon sınıfı aslında farklı türlerdir. Bu, şablon sınıflarının derleme sınırları genelinde kullanılamayacağı anlamına gelir.

Çapraz derleme paylaşımını mümkün kılmak için, STL/CLR kapsayıcıları genel arabirimi uygular <xref:System.Collections.Generic.ICollection%601> . Bu genel arabirimi kullanarak, C++, C# ve Visual Basic dahil olmak üzere genel türleri destekleyen tüm diller STL/CLR kapsayıcılarına erişebilir.

Bu konu başlığı altında, adlı bir C++ derlemesinde yazılmış çeşitli STL/CLR kapsayıcılarının öğelerinin nasıl görüntüleneceği gösterilmektedir `StlClrClassLibrary` . Erişmek için iki derleme gösteriyoruz `StlClrClassLibrary` . İlk derleme C++ dilinde, ikincisi ise C# dilinde yazılır.

Her iki derleme da C++ dilinde yazılmışsa, bir kapsayıcının genel arabirimine typedef öğesini kullanarak erişebilirsiniz `generic_container` . Örneğin, türünde bir kapsayıcınız varsa `cliext::vector<int>` , genel arabirimi: `cliext::vector<int>::generic_container` . Benzer şekilde, genel arabirim üzerinde, TypeDef ile olduğu gibi bir yineleyici alabilirsiniz `generic_iterator` : `cliext::vector<int>::generic_iterator` .

Bu tür tanımları 'ler C++ başlık dosyalarında bildirildiği için, diğer dillerde yazılmış derlemeler bunları kullanamaz. Bu nedenle, `cliext::vector<int>` C# veya başka bir .net dilinde için genel arabirime erişmek için kullanın `System.Collections.Generic.ICollection<int>` . Bu koleksiyonu yinelemek için bir `foreach` döngü kullanın.

Aşağıdaki tabloda her bir STL/CLR kapsayıcısının uyguladığı genel arabirim listelenmektedir:

|STL/CLR kapsayıcısı|Genel arabirim|
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
> `queue`, `priority_queue` Ve `stack` kapsayıcıları yineleyiciler desteklemediğinden, bunlar genel arabirimler uygulamaz ve çapraz derlemeye erişilemez.

## <a name="example-1"></a>Örnek 1

### <a name="description"></a>Açıklama

Bu örnekte, özel STL/CLR üye verilerini içeren bir C++ sınıfı bildiririz. Daha sonra, sınıfının özel koleksiyonlarına erişim vermek için ortak Yöntemler bildiririz. Biri C++ istemcileri ve diğeri de diğer .NET istemcileri için olmak üzere iki farklı şekilde yapılır.

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

Bu örnekte, örnek 1 ' de belirtilen sınıfı uyguladık. İstemcilerin bu sınıf kitaplığını kullanabilmesi için, bildirim dosyasını DLL 'ye eklemek üzere **mt.exe** bildirim aracını kullanırız. Ayrıntılar için bkz. kod açıklamaları.

Bildirim Aracı ve yan yana derlemeler hakkında daha fazla bilgi için bkz. [C/C++ yalıtılmış uygulamalar ve yan yana derlemeler oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).

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

Bu örnekte, 1 ve 2. örneklerde oluşturulan sınıf kitaplığını kullanan bir C++ istemcisi oluşturacağız. Bu istemci, `generic_container` kapsayıcıları yinelemek ve içeriklerini göstermek için STL/CLR kapsayıcılarının tür tanımları değerlerini kullanır.

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

### <a name="output"></a>Çıktı

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

Bu örnekte, 1 ve 2. örneklerde oluşturulan sınıf kitaplığını kullanan bir C# istemcisi oluşturacağız. Bu istemci, <xref:System.Collections.Generic.ICollection%601> kapsayıcıları yinelemek ve içeriklerini göstermek IÇIN STL/CLR kapsayıcılarının yöntemlerini kullanır.

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

### <a name="output"></a>Çıktı

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

## <a name="see-also"></a>Ayrıca bkz.

[STL/CLR kitaplık başvurusu](../dotnet/stl-clr-library-reference.md)
