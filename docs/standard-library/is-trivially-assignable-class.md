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
f1_keywords: type_traits/std::is_trivially_assignable
dev_langs: C++
helpviewer_keywords: is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4d40adc84ae8e2a9bb8f53e78d3a90dda99fd7e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [< type_traits >](../standard-library/type-traits.md)



