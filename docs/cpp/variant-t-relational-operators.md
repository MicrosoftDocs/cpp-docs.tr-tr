---
title: _variant_t ilişkisel işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08d7f5c7c244d242c3d1dd7af7d2c2af017bcc78
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948105"
---
# <a name="variantt-relational-operators"></a>_variant_t İlişkisel İşleçleri
**Microsoft'a özgü**  
  
 Karşılaştırabilirsiniz `_variant_t` eşitlik ve eşitsizlik için nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
bool operator==(  
   const VARIANT& varSrc) const;  
bool operator==(  
   const VARIANT* pSrc) const;  
bool operator!=(  
   const VARIANT& varSrc) const;  
bool operator!=(  
   const VARIANT* pSrc) const;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *varSrc*  
 A `VARIANT` ile Karşılaştırılacak `_variant_t` nesne.  
  
 *pSrc*  
 İşaretçi `VARIANT` ile Karşılaştırılacak `_variant_t` nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** karşılaştırma tutuyorsa **false** Aksi takdirde.  
  
## <a name="remarks"></a>Açıklamalar  
 Karşılaştıran bir `_variant_t` nesnesi ile bir `VARIANT`, eşitlik ve eşitsizlik için test etme.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)