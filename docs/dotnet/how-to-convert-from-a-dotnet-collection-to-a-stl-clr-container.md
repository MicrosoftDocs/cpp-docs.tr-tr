---
title: 'Nasıl yapılır: bir .NET koleksiyonundan STL/CLR kapsayıcısına dönüştürme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR, converting from .NET collections
- STL/CLR Containers [STL/CLR]
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8b6469c035a1f0daca5c789525778aab1119c9f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-from-a-net-collection-to-a-stlclr-container"></a>Nasıl yapılır: Bir .NET Koleksiyonundan STL/CLR Kapsayıcısına Dönüştürme
Bu konu, kendi eşdeğer STL/CLR kapsayıcıları .NET koleksiyonları dönüştürmek gösterilmiştir. Örnek olarak bir .NET dönüştürme gösteriyoruz <xref:System.Collections.Generic.List%601> STL/CLR için [vektör](../dotnet/vector-stl-clr.md) ve bir .NET dönüştürmek nasıl <xref:System.Collections.Generic.Dictionary%602> STL/CLR için [harita](../dotnet/map-stl-clr.md), ancak tüm koleksiyonlar ve kapsayıcıları için benzer bir yordamdır .  
  
### <a name="to-create-a-container-from-a-collection"></a>Koleksiyondan bir kapsayıcı oluşturmak için  
  
1.  Tüm koleksiyon dönüştürmek için bir STL/CLR kapsayıcı oluşturmak ve koleksiyon oluşturucuya geçirin.  
  
     İlk örnek, bu yordamı gösterir.  
  
 -VEYA-  
  
1.  Genel bir STL/CLR kapsayıcı oluşturma bir [collection_adapter](../dotnet/collection-adapter-stl-clr.md) nesnesi. Bu şablon sınıfı bir .NET koleksiyonu arabirimi bağımsız değişken olarak alır. Hangi arabirimlerin desteklenen doğrulamak için bkz: [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md).  
  
2.  .NET koleksiyonunun içeriğini kapsayıcıya kopyalayın. Bu bir STL/CLR kullanarak yapılabilir [algoritması](../dotnet/algorithm-stl-clr.md), veya tarafından .NET koleksiyonu üzerinden yineleme yapma ve her öğenin bir kopyasını STL/CLR kapsayıcısına ekleniyor.  
  
     İkinci örneği, bu yordamı gösterir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, bir genel oluşturuyoruz <xref:System.Collections.Generic.List%601> ve 5 öğeleri ekleyin. Ardından, oluşturduğumuz bir `vector` alan oluşturucu kullanılarak bir <xref:System.Collections.Generic.IEnumerable%601> bağımsız değişken olarak.  
  
```  
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
  
## <a name="example"></a>Örnek  
 Bu örnekte, bir genel oluşturuyoruz <xref:System.Collections.Generic.Dictionary%602> ve 5 öğeleri ekleyin. Ardından, oluşturduğumuz bir `collection_adapter` sarmalamak için <xref:System.Collections.Generic.Dictionary%602> basit bir STL/CLR kapsayıcı olarak. Son olarak, oluşturduğumuz bir `map` ve içeriğini kopyalayın <xref:System.Collections.Generic.Dictionary%602> için `map` üzerinde yineleme tarafından `collection_adapter`. Bu işlem sırasında yeni bir çift kullanarak oluşturuyoruz `make_pair` işlev ve doğrudan yeni çift Ekle `map`.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)   
 [Bağdaştırıcı (STL/CLR)](../dotnet/adapter-stl-clr.md)   
 [Nasıl yapılır: Bir STL/CLR Kapsayıcısından .NET Koleksiyonuna Dönüştürme](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)