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
ms.openlocfilehash: 68ef72cfd256a2676c73223723f37374c50cb56f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948128"
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Microsoft'a özgü**  
  
 Bir dize için atar `_variant_t` nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
void SetString(const char* pSrc);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pSrc*  
 Karakter dizesine yönelik işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir Unicode bir ANSI karakter dizesine dönüştürür `BSTR` dize ve bunun için atar `_variant_t` nesne.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)