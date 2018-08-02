---
title: _variant_t::detach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs:
- C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 895df401ab10ae85641fd2eed9f7a9654916f33f
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465239"
---
# <a name="varianttdetach"></a>_variant_t::Detach
**Microsoft'a özgü**  
  
 Kapsüllenmiş ayırır `VARIANT` bu nesneden `_variant_t` nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VARIANT Detach( );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş `VARIANT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Ayıklar ve döndürür kapsüllenmiş `VARIANT`, bu temizler `_variant_t` yok olmadan nesne. Bu üye işlevi kaldırır `VARIANT` kapsülleme ve kümeleri `VARTYPE` bu `_variant_t` VT_EMPTY nesnesine. Döndürülen yayın size olan `VARIANT` çağırarak [VariantClear](http://msdn.microsoft.com/28741d81-8404-4f85-95d3-5c209ec13835) işlevi.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)