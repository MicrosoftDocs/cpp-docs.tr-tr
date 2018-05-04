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
ms.openlocfilehash: b53d6dc51117ffe9b82511c6084e36bc49873b88
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="varianttdetach"></a>_variant_t::Detach
**Microsoft özel**  
  
 Kapsüllenmiş ayırır **değişken** bu nesneden `_variant_t` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
VARIANT Detach( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş **değişken**.  
  
## <a name="remarks"></a>Açıklamalar  
 Ayıklar ve kapsüllenmiş döndürür **değişken**, bu temizler `_variant_t` onu yok etme olmadan nesnesi. Bu üye işlevi kaldırır **değişken** kapsülleme ve ayarlar **VARTYPE** bu `_variant_t` nesnesine `VT_EMPTY`. Döndürülen yayın size olan **değişken** çağırarak [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) işlevi.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)