---
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 43dd21297ddd54863d535402dddd59243d589eec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180530"
---
# <a name="_com_errorsource"></a>_com_error::Source

**Microsoft 'a özgü**

`IErrorInfo::GetSource` işlevini çağırır.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t Source() const;
```

## <a name="return-value"></a>Dönüş Değeri

`_com_error` nesnesi içinde kaydedilen `IErrorInfo` nesnesi için `IErrorInfo::GetSource` sonucunu döndürür. Elde edilen `BSTR`, bir `_bstr_t` nesnesi içinde kapsüllenir. Kayıtlı `IErrorInfo` yoksa boş bir `_bstr_t`döndürür.

## <a name="remarks"></a>Açıklamalar

`IErrorInfo::GetSource` yöntemi çağrılırken herhangi bir hata yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)
