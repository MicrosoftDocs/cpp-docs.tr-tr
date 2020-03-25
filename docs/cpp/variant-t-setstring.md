---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: 0cd300a09c29668c496d93109d1bc862947e948c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187563"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Microsoft 'a özgü**

Bu `_variant_t` nesnesine bir dize atar.

## <a name="syntax"></a>Sözdizimi

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Parametreler

*pSrc*<br/>
Karakter dizesinin işaretçisi.

## <a name="remarks"></a>Açıklamalar

Bir ANSI karakter dizesini Unicode `BSTR` dizesine dönüştürür ve bu `_variant_t` nesnesine atar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
