---
title: 'Nasıl yapılır: bir STL/CLR kapsayıcısından .NET koleksiyonuna dönüştürme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7fb4938121d1d2beed3133bee6013e17d37f1402
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132014"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>Nasıl yapılır: Bir STL/CLR Kapsayıcısından .NET Koleksiyonuna Dönüştürme
Bu konu, STL/CLR kapsayıcıları kendi eşdeğer .NET koleksiyonlarına dönüştürme gösterilmektedir. Örnek olarak, bir STL/CLR dönüştürme gösteriyoruz [vektör](../dotnet/vector-stl-clr.md) bir .NET için <xref:System.Collections.Generic.ICollection%601> ve STL/CLR dönüştürmek nasıl [harita](../dotnet/map-stl-clr.md) bir .NET için <xref:System.Collections.Generic.IDictionary%602>, ancak tüm koleksiyonlar için benzer bir yordamdır ve kapsayıcı.  
  
### <a name="to-create-a-collection-from-a-container"></a>Bir kapsayıcı bir koleksiyon oluşturmak için  
  
1.  Aşağıdaki yöntemlerden birini kullanın:  
  
    -   Bir kapsayıcı parçası dönüştürmek için çağrı [make_collection](../dotnet/make-collection-stl-clr.md) işlev ve son yineleyici STL/CLR kapsayıcısı ve başlangıç yineleyici .NET koleksiyonuna kopyalanacak geçirin. Bu şablon işlevi bir STL/CLR yineleyici şablonu bağımsız değişken olarak alır. Bu yöntem ilk örneği gösterilmektedir.  
  
    -   Kapsayıcının tamamı dönüştürmek için uygun .NET koleksiyonu arabirim veya arabirim koleksiyonu kapsayıcıya dönüştürün. İkinci örnekte bu yöntem gösterilmektedir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, bir STL/CLR oluşturuyoruz `vector` ve 5 öğeleri ekleyin. Ardından, bir .NET koleksiyon çağırarak oluşturuyoruz `make_collection` işlevi. Son olarak, yeni oluşturulan koleksiyonunun içeriğini görüntüler.  
  
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
 Bu örnekte, bir STL/CLR oluşturuyoruz `map` ve 5 öğeleri ekleyin. Ardından, bir .NET oluşturuyoruz <xref:System.Collections.Generic.IDictionary%602> ve Ata `map` doğrudan. Son olarak, yeni oluşturulan koleksiyonunun içeriğini görüntüler.  
  
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
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)   
 [Nasıl yapılır: bir .NET koleksiyonundan STL/CLR kapsayıcısına dönüştürme](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)