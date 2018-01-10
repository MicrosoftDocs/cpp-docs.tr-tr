---
title: Vector::const_iterator (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::const_iterator
dev_langs: C++
helpviewer_keywords: const_iterator member [STL/CLR]
ms.assetid: 09c0ae0b-248b-463c-8f57-59c77eba1eaa
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 95b60c25e7da1c6196f6454df227c8e556b65318
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorconstiterator-stlclr"></a>vector::const_iterator (STL/CLR)
Denetlenen dizi için bir sabit yineleyici türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef T2 const_iterator;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T2` hizmet eden bir sabit rasgele erişim yineleyici denetlenen dizisi olarak.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_const_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::iterator (STL/CLR)](../dotnet/vector-iterator-stl-clr.md)