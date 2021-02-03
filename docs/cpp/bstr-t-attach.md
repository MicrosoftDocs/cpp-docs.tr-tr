---
description: ': _Bstr_t:: Attach hakkında daha fazla bilgi edinin'
title: _bstr_t::Attach
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.openlocfilehash: 02717fad98e4d68dde70995abcfad4cb55b8c45c
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522895"
---
# `_bstr_t::Attach`

**Microsoft'a Özgü**

Bir `_bstr_t` sarmalayıcısı öğesine bağlar `BSTR` .

## <a name="syntax"></a>Sözdizimi

```cpp
void Attach(
   BSTR s
);
```

### <a name="parameters"></a>Parametreler

*`s`*\
`BSTR` değişkeniyle ilişkilendirilecek veya ona atanacak bir `_bstr_t`.

## <a name="remarks"></a>Açıklamalar

`_bstr_t` daha önce başka bir `BSTR` öğesine eklenmişse, `_bstr_t``BSTR` kaynağını temizler (başka hiçbir `_bstr_t` değişkeni `BSTR` öğesini kullanmıyorsa).

## <a name="example"></a>Örnek

[`_bstr_t::Assign`](../cpp/bstr-t-assign.md)Bir örnek için bkz **`Attach`** ..

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`_bstr_t` Sınıfı](../cpp/bstr-t-class.md)
