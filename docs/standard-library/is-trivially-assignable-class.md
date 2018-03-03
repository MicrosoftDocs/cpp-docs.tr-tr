---
title: "is_trivially_assignable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 888c57de7cf83dda35f5d0cc114abed30fbb2115
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable sınıfı
Bir değeri olup olmadığını sınar `From` türü trivially atanabilen `To` türü  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class To, class From>  
struct is_trivially_assignable;
```  
  
#### <a name="parameters"></a>Parametreler  
 Bitiş  
 Atamayı alan nesnesi türü.  
  
 Başlangıç  
 Değer sağlayan nesne türü.  
  
## <a name="remarks"></a>Açıklamalar  
 İfade `declval<To>() = declval<From>()` doğru biçimlendirilmiş olması gerekir ve derleyici hiçbir Önemsiz olmayan işlemleri gerektirecek şekilde bilinmelidir. Her ikisi de `From` ve `To` tam tür `void`, veya bilinmeyen bağlı dizileri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



