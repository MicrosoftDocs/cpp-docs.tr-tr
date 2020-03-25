---
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: ca78bd1b607ba4a86bbc824887a7ec767cd5476e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181258"
---
# <a name="_bstr_tgetaddress"></a>_bstr_t::GetAddress

**Microsoft 'a özgü**

Varolan bir dizeyi boşaltır ve yeni ayrılan bir dizenin adresini döndürür.

## <a name="syntax"></a>Sözdizimi

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>Dönüş Değeri

`BSTR` tarafından sarmalanan bir `_bstr_t` işaretçisi.

## <a name="remarks"></a>Açıklamalar

**GetAddress** , bir `BSTR`paylaşan tüm `_bstr_t` nesnelerini etkiler. Birden fazla `_bstr_t`, kopya Oluşturucusu ve **işleç =** kullanımı aracılığıyla bir `BSTR` paylaşabilir.

## <a name="example"></a>Örnek

Bkz. [_bstr_t:: atama](../cpp/bstr-t-assign.md) , **GetAddress**kullanarak bir örnek için.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)
