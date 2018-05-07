---
title: Vector::reserve (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::reserve
dev_langs:
- C++
helpviewer_keywords:
- reserve member [STL/CLR]
ms.assetid: d1d5ede9-9628-4b55-95ec-f087a57205f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6c9c8bbf48d9727ff726ccfb0acde286535aa454
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="vectorreserve-stlclr"></a>vector::reserve (STL/CLR)
Kapsayıcı için en düşük büyüme kapasitesi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void reserve(size_type count);  
```  
  
#### <a name="parameters"></a>Parametreler  
 count  
 Kapsayıcı yeni en az kapasitesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi sağlar `capacity()` henceforth en az döndürür `count`. Belirtilen boyuta büyümüştür kadar kapsayıcı denetimli dizisi için depolama tahsis değil emin olmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_reserve.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
capacity() = 4, ok = True  
capacity() = 9, ok = True  
```  
  
## <a name="description"></a>Açıklama  
 Burada, çok uzun olarak gösterilen tüm değerler gerçek kapasiteleri değişebilir Not `ok` testleri rapor true.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::Capacity (STL/CLR)](../dotnet/vector-capacity-stl-clr.md)   
 [vector::resize (STL/CLR)](../dotnet/vector-resize-stl-clr.md)