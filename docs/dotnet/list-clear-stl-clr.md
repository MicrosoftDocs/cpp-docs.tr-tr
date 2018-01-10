---
title: List::Clear (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::clear
dev_langs: C++
helpviewer_keywords: clear member [STL/CLR]
ms.assetid: 5aac9a64-52f6-4a73-8b24-e30ceedcbc20
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aeb17552a3ba8988de67cfe4d3530fd544b953f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="listclear-stlclr"></a>list::clear (STL/CLR)
Tüm öğeleri kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini etkili bir şekilde çağırır [list::erase (STL/CLR)](../dotnet/list-erase-stl-clr.md) `(` [list::begin (STL/CLR)](../dotnet/list-begin-stl-clr.md) `(),` [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md) `())`. Denetimli sırası boş olduğundan emin olmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_list_clear.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::erase (STL/CLR)](../dotnet/list-erase-stl-clr.md)