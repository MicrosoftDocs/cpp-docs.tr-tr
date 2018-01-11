---
title: hash_multimap::hash_delegate (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::hash_delegate
dev_langs: C++
helpviewer_keywords: hash_delegate member [STL/CLR]
ms.assetid: 2a459f6d-9bb1-4b03-a013-0998ba842c25
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1c5fac0d4384b61a8e388ddc22f76a265818c1b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultimaphashdelegate-stlclr"></a>hash_multimap::hash_delegate (STL/CLR)
Belirtilen bir anahtarla eşleşen bir öğeyi bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
hasher^ hash_delegate();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi bir anahtar değeri bir tamsayıya dönüştürmek için kullanılan temsilci döndürür. Bir anahtar karma için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_hash_multimap_hash_delegate.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    Myhash_multimap::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 1616896120  
hash(L'b') = 570892832  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::hasher (STL/CLR)](../dotnet/hash-multimap-hasher-stl-clr.md)