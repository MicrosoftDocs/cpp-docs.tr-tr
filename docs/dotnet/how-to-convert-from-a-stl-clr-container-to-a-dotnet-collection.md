---
title: 'Nasıl yapılır: Bir STL/CLR Kapsayıcısından .NET Koleksiyonuna Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
ms.openlocfilehash: 3444339f43f8000d8a9c9b8a6577adb286245dbb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621630"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>Nasıl yapılır: Bir STL/CLR Kapsayıcısından .NET Koleksiyonuna Dönüştürme

Bu konuda, STL/CLR kapsayıcıları, eşdeğer bir .NET koleksiyonlarına dönüştürme gösterilmektedir. Örnek olarak, STL/CLR nasıl dönüştürme yapılacağını göstereceğiz [vektör](../dotnet/vector-stl-clr.md) kullanarak bir .NET <xref:System.Collections.Generic.ICollection%601> ve STL/CLR dönüştürme [harita](../dotnet/map-stl-clr.md) kullanarak bir .NET <xref:System.Collections.Generic.IDictionary%602>, ancak tüm koleksiyonlar için benzer bir yordamı ve kapsayıcıları.

### <a name="to-create-a-collection-from-a-container"></a>Bir koleksiyonu bir kapsayıcı oluşturmak için

1. Aşağıdaki yöntemlerden birini kullanın:

   - Bir kapsayıcı parçası dönüştürmek için çağrı [make_collection](../dotnet/make-collection-stl-clr.md) işlev ve başlangıç Yineleyici ve STL/CLR kapsayıcısına bitiş yineleyicisi .NET koleksiyonuna kopyalanacak geçirin. Bu şablon işlevi, bir şablon bağımsız değişkeni bir STL/CLR yineleyici alır. Bu yöntem ilk örnek gösterilmektedir.

   - Bir kapsayıcının tamamını dönüştürmek için kapsayıcı bir uygun .NET koleksiyon arabirimi veya arabirim koleksiyonu cast. İkinci örnek, bu yöntem gösterilmektedir.

## <a name="example"></a>Örnek

Bu örnekte, oluşturduğumuz bir STL/CLR `vector` ve 5 öğeleri ekleyin. Ardından, bir .NET koleksiyonunun çağırarak oluştururuz `make_collection` işlevi. Son olarak, yeni oluşturulan koleksiyonun içeriğini görüntüler.

```
// cliext_convert_vector_to_icollection.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/vector>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::vector<int> primeNumbersCont;
    primeNumbersCont.push_back(2);
    primeNumbersCont.push_back(3);
    primeNumbersCont.push_back(5);
    primeNumbersCont.push_back(7);
    primeNumbersCont.push_back(11);

    System::Collections::Generic::ICollection<int> ^iColl =
        make_collection<cliext::vector<int>::iterator>(
            primeNumbersCont.begin() + 1,
            primeNumbersCont.end() - 1);

    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");
    for each (int i in iColl)
    {
        Console::WriteLine(i);
    }
}
```

```Output
The contents of the System::Collections::Generic::ICollection are:
3
5
7
```

## <a name="example"></a>Örnek

Bu örnekte, oluşturduğumuz bir STL/CLR `map` ve 5 öğeleri ekleyin. Ardından, bir .NET oluştururuz <xref:System.Collections.Generic.IDictionary%602> ve atama `map` doğrudan. Son olarak, yeni oluşturulan koleksiyonun içeriğini görüntüler.

```
// cliext_convert_map_to_idictionary.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/map>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));

    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;

    Console::WriteLine("The contents of the IDictionary are:");
    for each (KeyValuePair<float, int> ^kvp in iDict)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);
    }
}
```

```Output
The contents of the IDictionary are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>Ayrıca Bkz.

[STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)<br/>
[Nasıl yapılır: Bir .NET Koleksiyonundan STL/CLR Kapsayıcısına Dönüştürme](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
[range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)