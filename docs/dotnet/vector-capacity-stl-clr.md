---
title: Vector::Capacity (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::capacity
dev_langs:
- C++
helpviewer_keywords:
- capacity member [STL/CLR]
ms.assetid: f82d8da9-8b4d-4288-8d18-8e9ca5911d87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9a08766c6b23deb4e36ad8c83f9c1f3e2bc1df1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167573"
---
# <a name="vectorcapacity-stlclr"></a>vector::capacity (STL/CLR)
Kapsayıcı için ayrılan depolama alanı boyutunu raporlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_type capacity();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi şu anda denetlenen sırası, en az kadar büyük bir değer tutmak için ayrılan depolama alanı döndürür [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`()`. Denetimli dizisi için depolama tahsis gerekir önce ne kadar kapsayıcı büyüyebilir belirlemek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_capacity.cpp   
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
 [vector::reserve (STL/CLR)](../dotnet/vector-reserve-stl-clr.md)