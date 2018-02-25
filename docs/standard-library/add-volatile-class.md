---
title: "add_volatile sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0425a4b9832b21b0b77c1f2098e9b9d359da7b91
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="addvolatile-class"></a>add_volatile Sınıfı
Bir değişken türü belirtilen türden yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty>  
struct add_volatile;  
 
template <class T>
using add_volatile_t = typename add_volatile<T>::type;  
```  
  
### <a name="parameters"></a>Parametreler  
*T*  
Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
Örneği `add_volatile<T>` üye typedef sahip `type` diğer bir deyişle *T* varsa *T* başvuru, bir işlev veya bir geçici nitelenmiş tür Aksi takdirde değer `volatile` *T*. Diğer ad `add_volatile_t` üye typedef erişmek için bir kısayol `type`. 
  
## <a name="example"></a>Örnek  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_volatile_t<int> *p = (volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_volatile<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
} 
```  
  
```Output  
add_volatile<int> == int  
```  
  
## <a name="requirements"></a>Gereksinimler  

**Başlık:** \<type_traits >  
  
**Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[<type_traits>](../standard-library/type-traits.md)   
[remove_volatile Sınıfı](../standard-library/remove-volatile-class.md)
