---
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: 775adfa7d5dd5aca098edcd793c2164d65fe7efa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190228"
---
# <a name="_com_errorhelpfile"></a>_com_error::HelpFile

**Microsoft 'a özgü**

`IErrorInfo::GetHelpFile` işlevini çağırır.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>Dönüş Değeri

`_com_error` nesnesi içinde kaydedilen `IErrorInfo` nesnesi için `IErrorInfo::GetHelpFile` sonucunu döndürür. Elde edilen BSTR, `_bstr_t` nesnesinde kapsüllenir. Kayıtlı `IErrorInfo` yoksa boş bir `_bstr_t`döndürür.

## <a name="remarks"></a>Açıklamalar

`IErrorInfo::GetHelpFile` yöntemi çağrılırken herhangi bir hata yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)
