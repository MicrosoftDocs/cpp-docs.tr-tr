---
title: "is_nothrow_assignable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_nothrow_assignable
dev_langs: C++
helpviewer_keywords: is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5bc98560000cc0f12270a55547aa0ee082d312a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable sınıfı
Değeri olup olmadığını sınar `From` türü atanabilen `To` türü ve atama değil atmak için bilinir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class To, class From>  
struct is_nothrow_assignable;
```  
  
#### <a name="parameters"></a>Parametreler  
 Bitiş  
 Atamayı alan nesnesi türü.  
  
 Başlangıç  
 Değer sağlayan nesne türü.  
  
## <a name="remarks"></a>Açıklamalar  
 İfade `declval<To>() = declval<From>()` doğru biçimlendirilmiş olması gerekir ve derleyiciye değil throw bilinmesi gerekir. Her ikisi de `From` ve `To` tam tür `void`, veya bilinmeyen bağlı dizileri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)



