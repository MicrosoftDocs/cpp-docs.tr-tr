---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: bir .NET koleksiyonundan STL/CLR kapsayıcısına dönüştürme'
title: 'Nasıl yapılır: Bir .NET Koleksiyonundan STL/CLR Kapsayıcısına Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR, converting from .NET collections
- STL/CLR Containers [STL/CLR]
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
ms.openlocfilehash: ba3e4ce6b9d7bd1c5da373c6eb545eb8167942b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268398"
---
# <a name="how-to-convert-from-a-net-collection-to-a-stlclr-container"></a>Nasıl yapılır: Bir .NET Koleksiyonundan STL/CLR Kapsayıcısına Dönüştürme

Bu konu başlığında, .NET koleksiyonlarının eşdeğer STL/CLR kapsayıcılarına nasıl dönüştürüleceği gösterilmektedir. Örnek olarak, bir .NET <xref:System.Collections.Generic.List%601> ' i STL/CLR [vektörüne](../dotnet/vector-stl-clr.md) nasıl dönüştürebileceğiniz ve bir .net <xref:System.Collections.Generic.Dictionary%602> STL/CLR [eşlemesine](../dotnet/map-stl-clr.md)nasıl dönüştüreceğiniz, ancak yordam tüm koleksiyonlar ve kapsayıcılar için benzerdir.

### <a name="to-create-a-container-from-a-collection"></a>Bir koleksiyondan kapsayıcı oluşturmak için

1. Tüm bir koleksiyonu dönüştürmek için bir STL/CLR kapsayıcısı oluşturun ve koleksiyonu oluşturucuya geçirin.

   İlk örnekte bu yordam gösterilmektedir.

-VEYA-

1. [Collection_adapter](./adapter-stl-clr.md#collection_adapter) nesnesi oluşturarak genel bir STL/CLR kapsayıcısı oluşturun. Bu şablon sınıfı bir .NET koleksiyon arabirimini bağımsız değişken olarak alır. Desteklenen arabirimlerin doğrulanması için bkz. [collection_adapter (STL/CLR)](./adapter-stl-clr.md#collection_adapter).

1. .NET koleksiyonunun içeriğini kapsayıcıya kopyalayın. Bu, STL/CLR [algoritması](../dotnet/algorithm-stl-clr.md)kullanılarak veya .net koleksiyonunun üzerine giderek ve her öğenin BIR kopyasını STL/CLR kapsayıcısına ekleyerek yapılabilir.

   İkinci örnekte bu yordam gösterilmektedir.

## <a name="examples"></a>Örnekler

Bu örnekte, bir genel oluşturacağız <xref:System.Collections.Generic.List%601> ve buna 5 öğe ekleyeceğiz. Sonra, bir `vector` bağımsız değişken olarak bir olarak alan oluşturucuyu kullanarak oluşturuyoruz <xref:System.Collections.Generic.IEnumerable%601> .

```cpp
// cliext_convert_list_to_vector.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/vector>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    List<int> ^primeNumbersColl = gcnew List<int>();
    primeNumbersColl->Add(2);
    primeNumbersColl->Add(3);
    primeNumbersColl->Add(5);
    primeNumbersColl->Add(7);
    primeNumbersColl->Add(11);

    cliext::vector<int> ^primeNumbersCont =
        gcnew cliext::vector<int>(primeNumbersColl);

    Console::WriteLine("The contents of the cliext::vector are:");
    cliext::vector<int>::const_iterator it;
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)
    {
        Console::WriteLine(*it);
    }
}
```

```Output
The contents of the cliext::vector are:
2
3
5
7
11
```

Bu örnekte, bir genel oluşturacağız <xref:System.Collections.Generic.Dictionary%602> ve buna 5 öğe ekleyeceğiz. Ardından, öğesini basit bir `collection_adapter` <xref:System.Collections.Generic.Dictionary%602> STL/CLR kapsayıcısı olarak kaydırmak için bir oluşturacağız. Son olarak, ' a bir oluşturur ve ' a ' `map` <xref:System.Collections.Generic.Dictionary%602> ye `map` yineleme yaparak içeriğini içine kopyalayın `collection_adapter` . Bu işlem sırasında, işlevini kullanarak yeni bir çift oluşturur `make_pair` ve yeni çifti doğrudan içine ekler `map` .

```cpp
// cliext_convert_dictionary_to_map.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/map>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    System::Collections::Generic::Dictionary<float, int> ^dict =
        gcnew System::Collections::Generic::Dictionary<float, int>();
    dict->Add(42.0, 42);
    dict->Add(13.0, 13);
    dict->Add(74.0, 74);
    dict->Add(22.0, 22);
    dict->Add(0.0, 0);

    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);
    cliext::map<float, int> aMap;
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)
    {
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);
        aMap.insert(aPair);
    }

    Console::WriteLine("The contents of the cliext::map are:");
    cliext::map<float, int>::const_iterator it;
    for (it = aMap.begin(); it != aMap.end(); it++)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);
    }
}
```

```Output
The contents of the cliext::map are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>Ayrıca bkz.

[STL/CLR kitaplık başvurusu](../dotnet/stl-clr-library-reference.md)<br/>
[bağdaştırıcı (STL/CLR)](../dotnet/adapter-stl-clr.md)<br/>
[Nasıl yapılır: STL/CLR Kapsayıcısından .NET koleksiyonuna dönüştürme](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)
