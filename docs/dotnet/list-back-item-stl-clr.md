---
title: List::back_item (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::back_item
dev_langs: C++
helpviewer_keywords: back_item member [STL/CLR]
ms.assetid: 63dcdd21-61f7-4e0f-88a7-c9c8f8a2c50a
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 295ab7a1cc96f5e961f5c6c375a904d45c4b1345
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="listbackitem-stlclr"></a>list::back_item (STL/CLR)
Son öğe erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
property value_type back_item;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Özelliği, son öğe boş olmalıdır denetimli dizisi erişir. Okumak veya mevcut bildiğinizde son öğe yazmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_list_back_item.cpp   
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
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back_item = c  
 a b x  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Back (STL/CLR)](../dotnet/list-back-stl-clr.md)   
 [List::Front (STL/CLR)](../dotnet/list-front-stl-clr.md)   
 [List::front_item (STL/CLR)](../dotnet/list-front-item-stl-clr.md)