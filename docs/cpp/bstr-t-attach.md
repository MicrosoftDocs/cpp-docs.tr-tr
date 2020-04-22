---
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: 718efb9e3dac0d776678fe9efd912a602e041659
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749693"
---
# <a name="_bstr_tattach"></a>_bstr_t::Attach

**Microsoft'a Özgü**

Bir `_bstr_t` sarıcıyı `BSTR`bir .

## <a name="syntax"></a>Sözdizimi

```cpp
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>Parametreler

*S*<br/>
`BSTR` değişkeniyle ilişkilendirilecek veya ona atanacak bir `_bstr_t`.

## <a name="remarks"></a>Açıklamalar

`_bstr_t` daha önce başka bir `BSTR` öğesine eklenmişse, `_bstr_t``BSTR` kaynağını temizler (başka hiçbir `_bstr_t` değişkeni `BSTR` öğesini kullanmıyorsa).

## <a name="example"></a>Örnek

Bkz. [_bstr_t::Ekle'yi](../cpp/bstr-t-assign.md) **Attach**kullanarak bir örnek için atama .

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)
