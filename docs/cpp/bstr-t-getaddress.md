---
title: _bstr_t::GetAddress | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b3aa001270a3dc608fabf73fce28ce51eb9295e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031307"
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress

**Microsoft'a özgü**

Varolan bir dizeyi boşaltır ve yeni ayrılan bir dizenin adresini döndürür.

## <a name="syntax"></a>Sözdizimi

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>Dönüş Değeri

`BSTR` tarafından sarmalanan bir `_bstr_t` işaretçisi.

## <a name="remarks"></a>Açıklamalar

**GetAddress** tüm etkiler `_bstr_t` nesneleri paylaşan bir `BSTR`. Birden fazla `_bstr_t` paylaşabileceğiniz bir `BSTR` kopya oluşturucu kullanılarak ve **işleç =**.

## <a name="example"></a>Örnek

Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) kullanarak bir örnek için **GetAddress**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)