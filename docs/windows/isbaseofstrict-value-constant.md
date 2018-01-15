---
title: Isbaseofstrict::Value sabiti | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs: C++
helpviewer_keywords: value constant
ms.assetid: 4a0cdab0-ba03-482b-babf-eeec519ba687
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 284cbe8b140d38b31017a97fef1910b3b63513b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="isbaseofstrictvalue-constant"></a>IsBaseOfStrict::value Sabiti
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const bool value = __is_base_of(Base, Derived);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir tür başka tabanı olup olmadığını gösterir.  
  
 `value`olan `true` varsa türü `Base` bir taban sınıf türü `Derived`, aksi takdirde değer `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Isbaseofstrict yapısı](../windows/isbaseofstrict-structure.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)