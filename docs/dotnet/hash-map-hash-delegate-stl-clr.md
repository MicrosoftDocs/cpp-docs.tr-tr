---
title: hash_map::hash_delegate (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::hash_delegate
dev_langs:
- C++
helpviewer_keywords:
- hash_delegate member [STL/CLR]
ms.assetid: ae451fbe-a10c-457f-9b54-94dd9d93e8c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bdc62608fc278332bce0d288ad9ac36de195401c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110414"
---
# <a name="hashmaphashdelegate-stlclr"></a>hash_map::hash_delegate (STL/CLR)
Belirtilen bir anahtarla eşleşen bir öğeyi bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
hasher^ hash_delegate();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevi bir anahtar değeri bir tamsayıya dönüştürmek için kullanılan temsilci döndürür. Bir anahtar karma için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_hash_map_hash_delegate.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    Myhash_map::hasher^ myhash = c1.hash_delegate();   
  
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
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::hasher (STL/CLR)](../dotnet/hash-map-hasher-stl-clr.md)