---
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: 3b52661097ca1feab4c8045be240e4138a0c0f21
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190670"
---
# <a name="_bstr_tattach"></a>_bstr_t::Attach

**Microsoft 'a özgü**

`_bstr_t` sarmalayıcısı bir `BSTR`bağlar.

## <a name="syntax"></a>Sözdizimi

```
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>Parametreler

*malar*<br/>
`BSTR` değişkeniyle ilişkilendirilecek veya ona atanacak bir `_bstr_t`.

## <a name="remarks"></a>Açıklamalar

`_bstr_t` daha önce başka bir `BSTR` öğesine eklenmişse, `_bstr_t``BSTR` kaynağını temizler (başka hiçbir `_bstr_t` değişkeni `BSTR` öğesini kullanmıyorsa).

## <a name="example"></a>Örnek

Bkz. [_bstr_t:: atama](../cpp/bstr-t-assign.md) kullanarak bir örnek **Attach**için atama.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)
