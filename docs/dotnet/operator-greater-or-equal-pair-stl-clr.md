---
title: "İşleç&gt;(eşleştirmesi) (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair::operator>=
dev_langs: C++
helpviewer_keywords: operator>= member [STL/CLR]
ms.assetid: dcc2decf-3b2b-495d-9fd5-3daba27d5096
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fa93ffbb83a4ebb5ea3e8e6a3987330f1c4aaba2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="operatorgt-pair-stlclr"></a>İşleç&gt;(eşleştirmesi) (STL/CLR)
Çifti daha büyük veya eşit karşılaştırma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator>=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol çifti.  
  
 sağ  
 Karşılaştırılacak sağ çifti.  
  
## <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left < right)`. Test etmek için kullandığınız olup olmadığını `left` önce sıralı değil `right` iki çift öğe tarafından karşılaştırılan öğe olduğunda.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_pair_operator_ge.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] >= [x 3] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] >= [x 3] is True  
[x 3] >= [x 4] is False  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/yardımcı programı >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [çift (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [operator == (çifti) (STL/CLR)](../dotnet/operator-equality-pair-stl-clr.md)   
 [operator! = (çifti) (STL/CLR)](../dotnet/operator-inequality-pair-stl-clr.md)   
 [İşleç\< (çifti) (STL/CLR)](../dotnet/operator-less-than-pair-stl-clr.md)   
 [operator > (çifti) (STL/CLR)](../dotnet/operator-greater-than-pair-stl-clr.md)   
 [operator < = (çifti) (STL/CLR)](../dotnet/operator-less-or-equal-pair-stl-clr.md)