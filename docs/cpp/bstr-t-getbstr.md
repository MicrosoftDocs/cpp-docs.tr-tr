---
description: ': _Bstr_t:: GetBSTR hakkında daha fazla bilgi'
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: ced985bb5123d86ff119279fc49a2b4d181ba8b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229307"
---
# <a name="_bstr_tgetbstr"></a>_bstr_t::GetBSTR

**Microsoft'a Özgü**

Tarafından Sarmalanan başlangıcını işaret eder `BSTR` `_bstr_t` .

## <a name="syntax"></a>Syntax

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>Dönüş Değeri

`BSTR`Tarafından Sarmalanan öğesinin başı `_bstr_t` .

## <a name="remarks"></a>Açıklamalar

**GetBSTR** `_bstr_t` , bir paylaşan tüm nesneleri etkiler `BSTR` . `_bstr_t` `BSTR` Kopya Oluşturucu ve **işleç =** kullanımı aracılığıyla bir tane daha fazlası paylaşabilir.

## <a name="example"></a>Örnek

**GetBSTR** kullanarak bir örnek için bkz. [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t sınıfı](../cpp/bstr-t-class.md)
