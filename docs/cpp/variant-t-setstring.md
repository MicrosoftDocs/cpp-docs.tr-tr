---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: d07e995be0ecd99974356a7516e7c4deee677637
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628247"
---
# <a name="varianttsetstring"></a>_variant_t::SetString

**Microsoft'a özgü**

Bir dize için atar `_variant_t` nesne.

## <a name="syntax"></a>Sözdizimi

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Parametreler

*pSrc*<br/>
Karakter dizesine yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

Bir Unicode bir ANSI karakter dizesine dönüştürür `BSTR` dize ve bunun için atar `_variant_t` nesne.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_variant_t Sınıfı](../cpp/variant-t-class.md)