---
title: 'Nasıl yapılır: Bir STL/CLR Kapsayıcısından .NET Koleksiyonuna Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
ms.openlocfilehash: f5e289c330c83ac0c630a5b1f8f97b8c65fc7efb
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686450"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>Nasıl yapılır: Bir STL/CLR Kapsayıcısından .NET Koleksiyonuna Dönüştürme

Bu konuda, STL/CLR kapsayıcılarının eşdeğer .NET koleksiyonlarına nasıl dönüştürüleceği gösterilmektedir. Örnek olarak, bir STL/CLR [vektörünü](../dotnet/vector-stl-clr.md) .net 'a nasıl dönüştüreceğiniz <xref:System.Collections.Generic.ICollection%601> ve STL/CLR [eşlemesinin](../dotnet/map-stl-clr.md) bir .net 'a nasıl dönüştürüleceği gösterilmektedir <xref:System.Collections.Generic.IDictionary%602> , ancak yordam tüm koleksiyonlar ve kapsayıcılar için benzerdir.

### <a name="to-create-a-collection-from-a-container"></a>Bir kapsayıcıdan koleksiyon oluşturmak için

1. Aşağıdaki yöntemlerden birini kullanın:

   - Bir kapsayıcının parçasını dönüştürmek için, [make_collection](../dotnet/make-collection-stl-clr.md) işlevini ÇAĞıRıN ve STL/CLR kapsayıcısının .net koleksiyonuna kopyalanmak üzere başlangıç yineleyicisini ve bitiş yineleyicisini geçirin. Bu şablon işlevi bir STL/CLR yineleyiciyi şablon bağımsız değişkeni olarak alır. İlk örnek bu yöntemi gösterir.

   - Kapsayıcının tamamını dönüştürmek için kapsayıcıyı uygun bir .NET koleksiyonu arabirimine veya arabirim koleksiyonuna atayın. İkinci örnek bu yöntemi gösterir.

## <a name="examples"></a>Örnekler

Bu örnekte, bir STL/CLR oluşturacağız `vector` ve buna 5 öğe ekleyeceğiz. Ardından, işlevini çağırarak bir .NET koleksiyonu oluşturacağız `make_collection` . Son olarak, yeni oluşturulan koleksiyonun içeriğini görüntüyoruz.

```cpp
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

Bu örnekte, bir STL/CLR oluşturacağız `map` ve buna 5 öğe ekleyeceğiz. Daha sonra bir .NET oluşturacağız <xref:System.Collections.Generic.IDictionary%602> ve `map` doğrudan buna atarız. Son olarak, yeni oluşturulan koleksiyonun içeriğini görüntüyoruz.

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[STL/CLR kitaplık başvurusu](../dotnet/stl-clr-library-reference.md)<br/>
[Nasıl yapılır: bir .NET koleksiyonundan STL/CLR kapsayıcısına dönüştürme](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
[range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)
