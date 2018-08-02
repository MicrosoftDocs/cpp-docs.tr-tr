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
ms.openlocfilehash: 090fd7ed027738ebe7bc9276e3b3f124b9212c4a
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463473"
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)