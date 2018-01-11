---
title: "is_assignable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_assignable
dev_langs: C++
helpviewer_keywords: is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba99c19328b576900b1c269c24949baa832c8be7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="isassignable-class"></a>is_assignable sınıfı
Bir değeri olup olmadığını sınar `From` türü atanabilen bir `To` türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class To, class From>  
struct is_assignable;
```  
  
#### <a name="parameters"></a>Parametreler  
 Bitiş  
 Atamayı alan nesnesi türü.  
  
 Başlangıç  
 Değer sağlayan nesne türü.  
  
## <a name="remarks"></a>Açıklamalar  
 Değerlendirilmeyecek ifade `declval<To>() = declval<From>()` doğru biçimlendirilmiş olması gerekir. Her ikisi de `From` ve `To` tam tür `void`, veya bilinmeyen bağlı dizileri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



