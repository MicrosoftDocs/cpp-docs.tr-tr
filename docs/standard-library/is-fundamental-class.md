---
title: "is_fundamental sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_fundamental
dev_langs: C++
helpviewer_keywords:
- is_fundamental class
- is_fundamental
ms.assetid: b84eee84-2fb2-4611-beaf-b384074d8b6a
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4469aa5c68c6fe021ad1d318128f34e29c82e1ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isfundamental-class"></a>is_fundamental Sınıfı
Test türü, void veya aritmetik ise.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty>  
struct is_fundamental;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `Ty` bir temel türü diğer bir deyişle, olup `void`, bir kayan bir tam sayı türü noktası türü, veya bir `cv-qualified` bunlardan biri, aksi takdirde false tuttuğu biçimidir.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// std__type_traits__is_fundamental.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_fundamental<trivial> == " << std::boolalpha   
        << std::is_fundamental<trivial>::value << std::endl;   
    std::cout << "is_fundamental<int> == " << std::boolalpha   
        << std::is_fundamental<int>::value << std::endl;   
    std::cout << "is_fundamental<const float> == " << std::boolalpha   
        << std::is_fundamental<const float>::value << std::endl;   
    std::cout << "is_fundamental<void> == " << std::boolalpha   
        << std::is_fundamental<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_fundamental<trivial> == false  
is_fundamental<int> == true  
is_fundamental<const float> == true  
is_fundamental<void> == true  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [is_compound sınıfı](../standard-library/is-compound-class.md)
