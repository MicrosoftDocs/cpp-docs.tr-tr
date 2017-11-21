---
title: _variant_t::ChangeType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs: C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8fea359c3f256d56f4d112fe93bb736a16892ea4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [_variant_t sınıfı](../cpp/variant-t-class.md)