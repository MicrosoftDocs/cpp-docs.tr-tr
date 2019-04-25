---
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 682070877f269967405677d027b20707c8366f61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154967"
---
# <a name="comerrorsource"></a>_com_error::Source

**Microsoft'a özgü**

Çağrıları `IErrorInfo::GetSource` işlevi.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t Source() const;
```

## <a name="return-value"></a>Dönüş Değeri

Sonucunu döndürür `IErrorInfo::GetSource` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Ortaya çıkan `BSTR` içinde kapsüllenir bir `_bstr_t` nesne. Hayır ise `IErrorInfo` olan kaydedilmemişse, boş bir döndürür `_bstr_t`.

## <a name="remarks"></a>Açıklamalar

Çağrılırken `IErrorInfo::GetSource` yöntemi göz ardı edilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)