---
title: _variant_t::SetString | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76aaf29febd04f95efc0922e0d2680976e1e97da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Microsoft özel**  
  
 Bir dize için atar `_variant_t` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void SetString(  
   const char* pSrc   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pSrc`  
 Karakter dizesi işaretçisi.  
  
## <a name="remarks"></a>Açıklamalar  
 ANSI karakter dizesi bir Unicode dönüştürür `BSTR` dize ve bunun için atar `_variant_t` nesnesi.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)