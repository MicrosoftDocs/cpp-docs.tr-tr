---
title: "_variant_t ilişkisel işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
dev_langs: C++
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eacfe9584cedfd45a952dca62dae545f617b1433
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="variantt-relational-operators"></a>_variant_t İlişkisel İşleçleri
**Microsoft özel**  
  
 İki karşılaştırmak `_variant_t` nesneleri eşitlik veya eşitsizlik.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *varSrc*  
 A **değişken** ile Karşılaştırılacak `_variant_t` nesnesi.  
  
 `pSrc`  
 İşaretçi **değişken** ile Karşılaştırılacak `_variant_t` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** karşılaştırma tutuyorsa **false** değilse.  
  
## <a name="remarks"></a>Açıklamalar  
 Karşılaştıran bir `_variant_t` nesnesi ile bir **değişken**, eşitlik veya eşitsizlik için sınama.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t sınıfı](../cpp/variant-t-class.md)