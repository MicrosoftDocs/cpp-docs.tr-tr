---
title: Vector::Empty (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::empty
dev_langs: C++
helpviewer_keywords: empty member [STL/CLR]
ms.assetid: c09fc4a3-bd79-4458-9a36-1d9c82ac36b1
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 63aafd2c817da8143512a777feed47feda03c62a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorempty-stlclr"></a>vector::empty (STL/CLR)
Bir öğe olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş denetimli dizisi için true değerini döndürür. Eşdeğer olan [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`() == 0`. Vektör boş olup olmadığını sınamak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_empty.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)