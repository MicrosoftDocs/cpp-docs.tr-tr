---
description: 'Daha fazla bilgi edinin: _bstr_t:: GetAddress'
title: _bstr_t::GetAddress
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.openlocfilehash: 23013a6666b8e268a6437532b69050933ffe6b42
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522839"
---
# `_bstr_t::GetAddress`

**Microsoft'a Özgü**

Varolan bir dizeyi boşaltır ve yeni ayrılan bir dizenin adresini döndürür.

## <a name="syntax"></a>Syntax

```cpp
BSTR* GetAddress( );
```

## <a name="return-value"></a>Dönüş Değeri

`BSTR` tarafından sarmalanan bir `_bstr_t` işaretçisi.

## <a name="remarks"></a>Açıklamalar

**`GetAddress`**`_bstr_t`, paylaşan tüm nesneleri etkiler `BSTR` . `_bstr_t` `BSTR` Kopyalama oluşturucusunun kullanımı ile birden çok arasında bir paylaşabilir **`operator=`** .

## <a name="example"></a>Örnek

Tarafından [`_bstr_t::Assign`](../cpp/bstr-t-assign.md) kullanılan bir örnek için bkz **`GetAddress`** ..

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`_bstr_t` sınıfı](../cpp/bstr-t-class.md)