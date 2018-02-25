---
title: "add_const sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::add_const
dev_langs:
- C++
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0aa9f967a04dabc49fb4e5e380a8f7f1d07899d2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="addconst-class"></a>add_const Sınıfı
Const türü türünden yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty>  
struct add_const;
```  
  
#### <a name="parameters"></a>Parametreler  
 `Ty`  
 Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir değişiklik-türü tür değiştiricisi örneğini tutan `Ty` varsa `Ty` başvuru, bir işlev veya bir const nitelenmiş tür Aksi takdirde değer `const Ty`.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// std__type_traits__add_const.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_const<int>::type *p = (const int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_const<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
add_const<int> == int  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_const Sınıfı](../standard-library/remove-const-class.md)
