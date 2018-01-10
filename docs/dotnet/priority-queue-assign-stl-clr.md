---
title: priority_queue::Assign (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::assign
dev_langs: C++
helpviewer_keywords: assign member [STL/CLR]
ms.assetid: 00cd3623-ecd0-4dde-ba5c-777c1c0bc0b5
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf9eec9f8e8905cbc22d670d0ca33b1f89eaa4b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueueassign-stlclr"></a>priority_queue::assign (STL/CLR)
Tüm öğeleri değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void assign(priority_queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 Eklemek için kapsayıcı Bağdaştırıcısı'nı tıklatın.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini atar `right.get_container()` temel kapsayıcısı. Sıranın tüm içeriğini değiştirmek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_priority_queue_assign.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Mypriority_queue c2;   
    c2.assign(c1);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
c a b  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::operator= (STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)