---
title: Vector::Capacity (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::capacity
dev_langs: C++
helpviewer_keywords: capacity member [STL/CLR]
ms.assetid: f82d8da9-8b4d-4288-8d18-8e9ca5911d87
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 97693360d03f0c861f1c2f1b956fcbd136d7c6f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Vector::reserve (STL/CLR)](../dotnet/vector-reserve-stl-clr.md)