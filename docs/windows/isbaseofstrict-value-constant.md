---
title: Isbaseofstrict::Value sabiti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs:
- C++
helpviewer_keywords:
- value constant
ms.assetid: 4a0cdab0-ba03-482b-babf-eeec519ba687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ac49319dca429dcc0351393f73d711266cf764a
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010778"
---
# <a name="isbaseofstrictvalue-constant"></a>IsBaseOfStrict::value Sabiti
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
static const bool value = __is_base_of(Base, Derived);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Başka bir taban bir türü olup olmadığını gösterir.  
  
 **değer** olduğu **true** , türü `Base` bir temel sınıf türünün `Derived`, aksi halde kalır **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Isbaseofstrict yapısı](../windows/isbaseofstrict-structure.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)