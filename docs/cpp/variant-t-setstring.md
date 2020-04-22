---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: 60ad1c1bd95eb35f2a4f2800f79d0326c68a1176
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745854"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Microsoft'a Özgü**

Bu `_variant_t` nesneye bir dize atar.

## <a name="syntax"></a>Sözdizimi

```cpp
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Parametreler

*pSrc*<br/>
Karakter dizesini işaretle.

## <a name="remarks"></a>Açıklamalar

ANSI karakter dizesini Unicode `BSTR` dizesine dönüştürür `_variant_t` ve bu nesneye atar.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)
