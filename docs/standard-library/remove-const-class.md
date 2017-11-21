---
title: "remove_const sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::remove_const
dev_langs: C++
helpviewer_keywords:
- remove_const class
- remove_const
ms.assetid: feb76fb3-9228-41d6-80f6-2fbb04daec43
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cbbe20b0b89a233be3f6250884968071f12971f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="removeconst-class"></a>remove_const Sınıfı
Türden sabit olmayan bir tür yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class T>  
struct remove_const;
```  
  
```  
template <class T>  
using remove_const_t = typename remove_const<T>::type;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Örneği `remove_const<T>` bir değişiklik-türü tutan `T1` zaman `T` biçimidir `const T1`, aksi takdirde `T`.  
  
## <a name="example"></a>Örnek  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_const_t<const int>*)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_const_t<const int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
remove_const_t<const int> == int  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [add_const sınıfı](../standard-library/add-const-class.md)   
 [remove_cv sınıfı](../standard-library/remove-cv-class.md)
