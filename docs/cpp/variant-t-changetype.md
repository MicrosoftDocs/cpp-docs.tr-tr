---
title: _variant_t::ChangeType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53fd73fc9606053dda6f8c143618373ad9bb7e4e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Microsoft özel**  
  
 Türünü değiştirir `_variant_t` belirtilen nesneye **VARTYPE**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `vartype`  
 **VARTYPE** bu `_variant_t` nesnesi.  
  
 `pSrc`  
 Bir işaretçi `_variant_t` dönüştürülecek nesne. Bu değer ise **NULL**, dönüştürme, yerinde yapılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi dönüştüren bir `_variant_t` belirtilen nesnesine **VARTYPE**. Varsa `pSrc` olan **NULL**, dönüştürme yerinde, aksi takdirde bu yapılır `_variant_t` nesne kopyalanan `pSrc` ve sonra dönüştürülür.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)