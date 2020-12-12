---
description: ': _Bstr_t:: Attach hakkında daha fazla bilgi edinin'
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: b3f29c8eaf81a492f7e3c4282227d3d6d246988e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229437"
---
# <a name="_bstr_tattach"></a>_bstr_t::Attach

**Microsoft'a Özgü**

Bir `_bstr_t` sarmalayıcısı öğesine bağlar `BSTR` .

## <a name="syntax"></a>Sözdizimi

```cpp
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>Parametreler

*s*<br/>
`BSTR` değişkeniyle ilişkilendirilecek veya ona atanacak bir `_bstr_t`.

## <a name="remarks"></a>Açıklamalar

`_bstr_t` daha önce başka bir `BSTR` öğesine eklenmişse, `_bstr_t``BSTR` kaynağını temizler (başka hiçbir `_bstr_t` değişkeni `BSTR` öğesini kullanmıyorsa).

## <a name="example"></a>Örnek

Bkz. [_bstr_t:: atama](../cpp/bstr-t-assign.md) kullanarak bir örnek için atama.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t sınıfı](../cpp/bstr-t-class.md)
