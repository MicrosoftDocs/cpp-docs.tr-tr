---
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: cea3404e0732cb0e16b3fa9199ce95e3dfcc23f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386154"
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR

**Microsoft'a özgü**

Başlangıcına işaret `BSTR` tarafından Sarmalanan `_bstr_t`.

## <a name="syntax"></a>Sözdizimi

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>Dönüş Değeri

Başlangıcı `BSTR` tarafından Sarmalanan `_bstr_t`.

## <a name="remarks"></a>Açıklamalar

**GetBSTR** tüm etkiler `_bstr_t` nesneleri paylaşan bir `BSTR`. Birden fazla `_bstr_t` paylaşabileceğiniz bir `BSTR` kopya oluşturucu kullanılarak ve **işleç =**.

## <a name="example"></a>Örnek

Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) bir örnek için **GetBSTR**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)