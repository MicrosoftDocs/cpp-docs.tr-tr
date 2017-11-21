---
title: "Extent sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::extent
dev_langs: C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 185cb6108801b31c19301a0f7488352a6948f5bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="extent-class"></a>extent Sınıfı
Bir dizi boyut alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty, unsigned I = 0>  
struct extent;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
 `I`  
 Dizi sorgu bağlanır.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `Ty` en az bir dizi türü `I` boyutları türü bir sorgu tutan öğelerin sayısı tarafından belirtilen boyutta `I`. Varsa `Ty` bir dizi türü değilse veya kendi derece değerinden `I`, veya `I` sıfır ve `Ty` türü "Bilinmeyen dizisi bağlı olarak `U`", 0 değeri türü bir sorgu tutar.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// std__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
extent 0 == 5  
extent 1 == 10  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [remove_all_extents sınıfı](../standard-library/remove-all-extents-class.md)   
 [remove_extent sınıfı](../standard-library/remove-extent-class.md)
