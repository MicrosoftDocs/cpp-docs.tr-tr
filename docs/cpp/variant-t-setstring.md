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
ms.openlocfilehash: 52ea719a2c9296ca1e64d881ac150994c041e206
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018736"
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