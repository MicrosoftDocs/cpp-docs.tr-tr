---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: HelpFile'
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: e45785913a8a5a1909f702bce672727171e0baef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295932"
---
# <a name="_com_errorhelpfile"></a>_com_error::HelpFile

**Microsoft'a Özgü**

Çağıran `IErrorInfo::GetHelpFile` işlevi.

## <a name="syntax"></a>Syntax

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>Dönüş Değeri

`IErrorInfo::GetHelpFile` `IErrorInfo` Nesne içinde kaydedilen nesnenin sonucunu döndürür `_com_error` . Elde edilen BSTR, `_bstr_t` nesnesinde kapsüllenir. Hiçbiri `IErrorInfo` kayıtlı değilse, boş döndürür `_bstr_t` .

## <a name="remarks"></a>Açıklamalar

Yöntemi çağırırken herhangi bir hata `IErrorInfo::GetHelpFile` yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error sınıfı](../cpp/com-error-class.md)
