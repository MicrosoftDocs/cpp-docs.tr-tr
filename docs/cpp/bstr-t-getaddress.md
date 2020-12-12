---
description: 'Daha fazla bilgi edinin: _bstr_t:: GetAddress'
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: afb877a6f1b4cfcfb6fe08b36168af745d733b85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229320"
---
# <a name="_bstr_tgetaddress"></a>_bstr_t::GetAddress

**Microsoft'a Özgü**

Varolan bir dizeyi boşaltır ve yeni ayrılan bir dizenin adresini döndürür.

## <a name="syntax"></a>Syntax

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>Dönüş Değeri

`BSTR` tarafından sarmalanan bir `_bstr_t` işaretçisi.

## <a name="remarks"></a>Açıklamalar

**GetAddress** `_bstr_t` , bir paylaşan tüm nesneleri etkiler `BSTR` . `_bstr_t` `BSTR` Kopya Oluşturucu ve **işleç =** kullanımı aracılığıyla bir tane daha fazlası paylaşabilir.

## <a name="example"></a>Örnek

Bkz. [_bstr_t:: atama](../cpp/bstr-t-assign.md) , **GetAddress** kullanarak bir örnek için.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t sınıfı](../cpp/bstr-t-class.md)
