---
title: "is_move_assignable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1003b77fcca3a5b0f6840f53d353c882e45a5ef3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ismoveassignable-class"></a>is_move_assignable sınıfı
Türü olabiliyorsa, testleri atanan taşıyın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>
struct is_move_assignable;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir türü taşıma atanabilir ise rvalue başvuru türüne bir başvuru türüne atanabilir. Türü koşulu eşdeğerdir `is_assignable<T&, T&&>`. Atanabilir türleri önerilebilir skaler türler ve taşıma atama işleçleri derleyicinin ürettiği veya kullanıcı tanımlı olan sınıf türünü taşıyın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



