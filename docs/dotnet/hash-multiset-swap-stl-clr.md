---
title: hash_multiset::Swap (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::swap
dev_langs:
- C++
helpviewer_keywords:
- swap member [STL/CLR]
ms.assetid: b79372ab-ca51-494a-89cf-4e2da3ee3ff7
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 28dfb2a37e2ffc68f92f7c976ae83c98b4f89e4b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisetswap-stlclr"></a>hash_multiset::swap (STL/CLR)
İki kapsayıcının içeriğinin yerini değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void swap(hash_multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 İçeriği ile değiştirilecek kapsayıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sıraları arasında değiştirir `this` ve `right`. Bunu Sabit sürede yapar ve hiçbir özel durum oluşturur. Bunu iki kapsayıcı içeriğini exchange hızlı bir şekilde kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_hash_multiset_swap.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    Myhash_multiset c2;   
    c2.insert(L'd');   
    c2.insert(L'e');   
    c2.insert(L'f');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
d e f  
d e f  
a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::operator= (STL/CLR)](../dotnet/hash-multiset-operator-assign-stl-clr.md)