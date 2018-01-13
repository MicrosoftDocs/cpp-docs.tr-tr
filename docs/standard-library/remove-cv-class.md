---
title: "remove_cv sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::remove_cv
dev_langs: C++
helpviewer_keywords:
- remove_cv class
- remove_cv
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 335d3d5cc2efef9a0a3f3e2642988dc44c3aa067
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="removecv-class"></a>remove_cv Sınıfı
Türden sabit/geçici olmayan tür yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class T>  
struct remove_cv;  
 
template <class T>  
using remove_cv_t = typename remove_cv<T>::type;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Örneği `remove_cv<T>` bir değişiklik-türü tutan `T1` zaman `T` biçimidir `const T1`, `volatile T1`, veya `const volatile T1`, aksi takdirde `T`.  
  
## <a name="example"></a>Örnek  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_cv_t<const volatile int> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_cv_t<const volatile int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
remove_cv_t<const volatile int> == int  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [remove_const sınıfı](../standard-library/remove-const-class.md)   
 [remove_volatile Sınıfı](../standard-library/remove-volatile-class.md)
