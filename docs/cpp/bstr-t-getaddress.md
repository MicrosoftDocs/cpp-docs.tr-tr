---
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: 4d51539d2afbb2fbcc860b6c4d821df119aca418
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393902"
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