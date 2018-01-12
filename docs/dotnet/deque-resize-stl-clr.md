---
title: deque::resize (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::deque::resize
dev_langs: C++
helpviewer_keywords: resize member [STL/CLR]
ms.assetid: c83f3c57-38b3-4706-a124-59bafbf88484
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fac11adade64d03696cbe73b09d1c35dfdd026b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dequeresize-stlclr"></a>deque::resize (STL/CLR)
Öğe sayısını değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>Parametreler  
 new_size  
 Denetimli sırası yeni büyüklüğü.  
  
 VAL  
 Doldurma öğesinin değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Her iki üye işlevleri emin [deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `()` henceforth döndürür `new_size`. Uzun denetimli dizisi yapmanız gerekiyorsa, ilk üye işlevi değer ile öğeleri ekler `value_type()`değere sahip öğeleri ikinci üye işlevi ekler yaparken `val`. Daha kısa denetimli sıra yapmak için her iki üye işlevleri etkili bir şekilde son öğe silme [deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `() -` `new_size` kez. Denetimli sırası boyutu olduğundan emin olmak için kullandığınız `new_size`, kırpma ya da geçerli denetimli dizisi doldurma tarafından.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::Clear (STL/CLR)](../dotnet/deque-clear-stl-clr.md)   
 [deque::ERASE (STL/CLR)](../dotnet/deque-erase-stl-clr.md)   
 [deque::insert (STL/CLR)](../dotnet/deque-insert-stl-clr.md)