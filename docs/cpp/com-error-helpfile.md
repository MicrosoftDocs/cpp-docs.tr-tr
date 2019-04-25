---
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: 826ac53f001355127f16b7ad2a7583a0f8800de7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155039"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile

**Microsoft'a özgü**

Çağrıları `IErrorInfo::GetHelpFile` işlevi.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>Dönüş Değeri

Sonucunu döndürür `IErrorInfo::GetHelpFile` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Elde edilen BSTR, `_bstr_t` nesnesinde kapsüllenir. Hayır ise `IErrorInfo` olan kaydedilmemişse, boş bir döndürür `_bstr_t`.

## <a name="remarks"></a>Açıklamalar

Çağrılırken `IErrorInfo::GetHelpFile` yöntemi göz ardı edilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)