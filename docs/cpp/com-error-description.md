---
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: a517c40e9adfbda2d790ce41a48ccf8658bcd3e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544397"
---
# <a name="comerrordescription"></a>_com_error::Description

**Microsoft'a özgü**

Çağrıları `IErrorInfo::GetDescription` işlevi.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>Dönüş Değeri

Sonucunu döndürür `IErrorInfo::GetDescription` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Ortaya çıkan `BSTR` içinde kapsüllenir bir `_bstr_t` nesne. Hayır ise `IErrorInfo` olan kaydedilmemişse, boş bir döndürür `_bstr_t`.

## <a name="remarks"></a>Açıklamalar

Çağrıları `IErrorInfo::GetDescription` işlevi ve alır `IErrorInfo` içinde kaydedilen `_com_error` nesne. Çağrılırken `IErrorInfo::GetDescription` yöntemi göz ardı edilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)