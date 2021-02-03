---
description: ': _Bstr_t:: GetBSTR hakkında daha fazla bilgi'
title: _bstr_t::GetBSTR
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.openlocfilehash: b48dd082b21c0f3416c8b58b8ae2669c74d9d227
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522761"
---
# `_bstr_t::GetBSTR`

**Microsoft'a Özgü**

Tarafından Sarmalanan başlangıcını işaret eder `BSTR` `_bstr_t` .

## <a name="syntax"></a>Syntax

```cpp
BSTR& GetBSTR( );
```

## <a name="return-value"></a>Dönüş Değeri

`BSTR`Tarafından Sarmalanan öğesinin başı `_bstr_t` .

## <a name="remarks"></a>Açıklamalar

**`GetBSTR`**`_bstr_t`, paylaşan tüm nesneleri etkiler `BSTR` . `_bstr_t` `BSTR` Kopyalama oluşturucusunun kullanımı ile birden çok arasında bir paylaşabilir `operator=` .

## <a name="example"></a>Örnek

Tarafından [`_bstr_t::Assign`](../cpp/bstr-t-assign.md) kullanılan bir örnek için bkz **`GetBSTR`** ..

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`_bstr_t` sınıfı](../cpp/bstr-t-class.md)