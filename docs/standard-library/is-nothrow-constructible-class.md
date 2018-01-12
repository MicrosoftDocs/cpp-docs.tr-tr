---
title: "is_nothrow_constructible sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_nothrow_constructible
dev_langs: C++
helpviewer_keywords: is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 02698c90714ae530e827d9bfbe6cdc7ce1fd0abf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="isnothrowconstructible-class"></a>is_nothrow_constructible sınıfı
Bir türü oluşturulabilir ve belirtilen bağımsız değişken türleri kullanıldığında throw değil bilinen olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class... Args>  
struct is_nothrow_constructible;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
 `Args`  
 Bir oluşturucuda eşleştirmek için bağımsız değişken türleri `T`.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` bağımsız değişken türleri oluşturulabilir kullanmaktır `Args`ve Oluşturucusu derleyici tarafından değil throw bilinen; Aksi halde false tutar. Tür `T` oluşturulabilir olduğundan, değişken tanımını `T t(std::declval<Args>()...);` doğru oluşturulmamış. Her ikisi de `T` ve içindeki tüm türler `Args` tam tür `void`, veya bilinmeyen bağlı dizileri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



