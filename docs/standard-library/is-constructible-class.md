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
ms.workload: cplusplus
ms.openlocfilehash: a2d2127ec8f007dbf301fca7e01a59a7ef462cd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [<type_traits>](../standard-library/type-traits.md)



