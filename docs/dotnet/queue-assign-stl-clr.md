---
title: Queue::Assign (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::assign
dev_langs: C++
helpviewer_keywords: assign member [STL/CLR]
ms.assetid: 5bec8a84-9561-43f7-ad7f-f845d0edef41
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9bb8391ddeee73e5a5f4b2ce63b7034079b64897
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="queueassign-stlclr"></a>queue::assign (STL/CLR)
Tüm öğeleri değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void assign(queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 Eklemek için kapsayıcı Bağdaştırıcısı'nı tıklatın.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini atar `right.get_container()` temel kapsayıcısı. Sıranın tüm içeriğini değiştirmek için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_queue_assign.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Myqueue c2;   
    c2.assign(c1);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [sıra (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Queue::operator (STL/CLR) =](../dotnet/queue-operator-assign-stl-clr.md)