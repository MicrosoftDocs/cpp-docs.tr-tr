---
title: _bstr_t::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1eddbc7a01be66430759bb84c3ce6d840f37d098
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111218"
---
# <a name="bstrtattach"></a>_bstr_t::Attach

**Microsoft'a özgü**

Bağlantılar bir `_bstr_t` sarmalayıcısını bir `BSTR`.

## <a name="syntax"></a>Sözdizimi

```
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

Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) bir örnek için **iliştirme**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)