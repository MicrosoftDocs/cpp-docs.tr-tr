---
title: "is_constructible sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_constructible
dev_langs: C++
helpviewer_keywords: is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f103b5a822faee69101c346f596aa2742a71cf99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isconstructible-class"></a>is_constructible sınıfı
Belirtilen bağımsız değişken türleri kullanıldığında bir türü oluşturulabilir olup olmadığını test eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class... Args>  
struct is_constructible;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
 `Args`  
 Bir oluşturucuda eşleştirmek için bağımsız değişken türleri `T`.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` bağımsız değişken türleri oluşturulabilir kullanmaktır `Args`, aksi takdirde false tutar. Tür `T` oluşturulabilir olduğundan, değişken tanımını `T t(std::declval<Args>()...);` doğru oluşturulmamış. Her ikisi de `T` ve içindeki tüm türler `Args` tam tür `void`, veya bilinmeyen bağlı dizileri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)



