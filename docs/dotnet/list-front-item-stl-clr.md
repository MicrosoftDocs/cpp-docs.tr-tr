---
title: List::front_item (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::front_item
dev_langs:
- C++
helpviewer_keywords:
- front_item member [STL/CLR]
ms.assetid: c871873b-7745-442b-9760-9d8096fa8610
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6c73cccb7c384caf8948d932c8d80ccf7c91d31d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131549"
---
# <a name="listfrontitem-stlclr"></a>list::front_item (STL/CLR)
İlk öğe erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
property value_type front_item;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Özelliği boş olması gerekir denetlenen dizisinin ilk öğesi erişir. Okumak veya mevcut bildiğinizde ilk öğe yazmak için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_list_front_item.cpp   
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
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front_item = a  
 x b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Back (STL/CLR)](../dotnet/list-back-stl-clr.md)   
 [List::back_item (STL/CLR)](../dotnet/list-back-item-stl-clr.md)   
 [list::front (STL/CLR)](../dotnet/list-front-stl-clr.md)