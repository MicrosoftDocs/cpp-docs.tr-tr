---
title: "is_compound sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_compound
dev_langs: C++
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 570a67a3b18bd9d2bf7652d604f1e4e3156664de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="iscompound-class"></a>is_compound Sınıfı
Belirtilen tür temel değilse testleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty>  
struct is_compound;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneğini tutan `false` varsa türünü `Ty` temel türü (varsa, diğer bir deyişle, [is_fundamental](../standard-library/is-fundamental-class.md) `<Ty>` tutan `true`); Aksi takdirde, bu `true`. Bu nedenle, koşul tutan `true` varsa `Ty` olan bir dizi türü, bir işlev türü için bir işaretçi `void` veya bir nesneye veya işlevi bir başvuru, sınıfı, bir UNION, bir numaralandırma veya işaretçi statik olmayan sınıf üyesi için bir veya bir  *MS tam* bunlardan birini biçimidir.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// std__type_traits__is_compound.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_compound<trivial> == " << std::boolalpha   
        << std::is_compound<trivial>::value << std::endl;   
    std::cout << "is_compound<int[]> == " << std::boolalpha   
        << std::is_compound<int[]>::value << std::endl;   
    std::cout << "is_compound<int()> == " << std::boolalpha   
        << std::is_compound<int()>::value << std::endl;   
    std::cout << "is_compound<int&> == " << std::boolalpha   
        << std::is_compound<int&>::value << std::endl;   
    std::cout << "is_compound<void *> == " << std::boolalpha   
        << std::is_compound<void *>::value << std::endl;   
    std::cout << "is_compound<int> == " << std::boolalpha   
        << std::is_compound<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_compound<trivial> == true  
is_compound<int[]> == true  
is_compound<int()> == true  
is_compound<int&> == true  
is_compound<void *> == true  
is_compound<int> == false  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [is_class sınıfı](../standard-library/is-class-class.md)
