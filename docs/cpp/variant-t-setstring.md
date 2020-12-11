---
description: ': _Variant_t:: SetString hakkında daha fazla bilgi'
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: a36bab9189b6046325bb275469dc9dbdb495fc7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161422"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Microsoft'a Özgü**

Bu nesneye bir dize atar `_variant_t` .

## <a name="syntax"></a>Sözdizimi

```cpp
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Parametreler

*pSrc*<br/>
Karakter dizesinin işaretçisi.

## <a name="remarks"></a>Açıklamalar

Bir ANSI karakter dizesini Unicode `BSTR` dizesine dönüştürür ve bu `_variant_t` nesneye atar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t sınıfı](../cpp/variant-t-class.md)
