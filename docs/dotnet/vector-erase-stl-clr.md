---
title: Vector::ERASE (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::erase
dev_langs: C++
helpviewer_keywords: erase member [STL/CLR]
ms.assetid: 624905eb-83c0-499b-a07a-c10aebd7acc3
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7edabb5d02b09944f5745a6d6cfc264fb120eade
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vectorerase-stlclr"></a>vector::erase (STL/CLR)
Belirtilen konumlardaki öğeleri kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Silme aralığını başlangıcı.  
  
 Son  
 Silinecek aralığı sonu.  
  
 Burada  
 Silinecek öğe.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi gösterdiği denetimli sırasının öğeyi kaldırır `where`. Tek bir öğe kaldırmak için kullanın.  
  
 İkinci üye işlevi denetlenen sıradaki aralığında kaldırır [`first`, `last`). Sıfır veya daha fazla bitişik öğeleri kaldırmak için kullanın.  
  
 Her iki üye işlevleri kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici dönün veya [vector::end (STL/CLR)](../dotnet/vector-end-stl-clr.md) `()` böyle bir öğe varsa.  
  
 Öğeleri silme, öğesi kopyaları kuvvetini sonuna bitişinde yakın arasındaki öğelerin sayısı doğrusal sayısıdır. (Bir veya daha fazla öğe sırası her iki ucundaki silme hiçbir öğe kopya oluşur.)  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_erase.cpp   
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
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::vector<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::Clear (STL/CLR)](../dotnet/vector-clear-stl-clr.md)