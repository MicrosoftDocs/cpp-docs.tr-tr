---
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: da438c65256d9a7e5bf5b02e108fee1385171d2d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181219"
---
# <a name="_bstr_tgetbstr"></a>_bstr_t::GetBSTR

**Microsoft 'a özgü**

`_bstr_t`kaydırılan `BSTR` başlangıcını işaret eder.

## <a name="syntax"></a>Sözdizimi

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>Dönüş Değeri

`_bstr_t`kaydırılan `BSTR` başlangıcı.

## <a name="remarks"></a>Açıklamalar

**GetBSTR** , bir `BSTR`paylaşan tüm `_bstr_t` nesnelerini etkiler. Birden fazla `_bstr_t`, kopya Oluşturucusu ve **işleç =** kullanımı aracılığıyla bir `BSTR` paylaşabilir.

## <a name="example"></a>Örnek

**GetBSTR**kullanarak bir örnek için bkz. [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)
