---
title: _variant_t::detach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs: C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 014de597ffbc9a7004f821393902ffe05ac1f278
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [_variant_t sınıfı](../cpp/variant-t-class.md)