---
title: "is_move_assignable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_move_assignable
dev_langs: C++
helpviewer_keywords: is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1db589d15042a5e94223aa0f711f58cb30da9983
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [< type_traits >](../standard-library/type-traits.md)



