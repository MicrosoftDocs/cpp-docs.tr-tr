---
title: "remove_extent sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::remove_extent
dev_langs: C++
helpviewer_keywords:
- remove_extent class
- remove_extent
ms.assetid: b9320862-3891-49fc-80bc-571eb2c035cf
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 06c2045065437e2b365f84b7464879036fd8ae33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="removeextent-class"></a>remove_extent Sınıfı
Dizi türünden öğe türü yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class T>  
struct remove_extent;  
 
template <class T>  
using remove_extent_t = typename remove_extent<T>::type;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Örneği `remove_extent<T>` bir değişiklik-türü tutan `T1` zaman `T` biçimidir `T1[N]`, aksi takdirde `T`.  
  
## <a name="example"></a>Örnek  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "remove_extent_t<int> == "  
        << typeid(std::remove_extent_t<int>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5]> == "  
        << typeid(std::remove_extent_t<int[5]>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5][10]> == "  
        << typeid(std::remove_extent_t<int[5][10]>).name()  
        << std::endl;   
    return (0);   
    }  
```  
  
```Output  
remove_extent_t<int> == int  
remove_extent_t<int[5]> == int  
remove_extent_t<int[5][10]> == int [10]  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [remove_all_extents Sınıfı](../standard-library/remove-all-extents-class.md)
