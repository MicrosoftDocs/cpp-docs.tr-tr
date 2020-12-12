---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: kaynak'
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 3b6cf35420454e8285d3d8b4deee3df8fe8771e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295776"
---
# <a name="_com_errorsource"></a>_com_error::Source

**Microsoft'a Özgü**

Çağıran `IErrorInfo::GetSource` işlevi.

## <a name="syntax"></a>Syntax

```
_bstr_t Source() const;
```

## <a name="return-value"></a>Dönüş Değeri

`IErrorInfo::GetSource` `IErrorInfo` Nesne içinde kaydedilen nesnenin sonucunu döndürür `_com_error` . Sonuç `BSTR` olarak bir nesne içinde kapsüllenir `_bstr_t` . Hiçbiri `IErrorInfo` kayıtlı değilse, boş döndürür `_bstr_t` .

## <a name="remarks"></a>Açıklamalar

Yöntemi çağırırken herhangi bir hata `IErrorInfo::GetSource` yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error sınıfı](../cpp/com-error-class.md)
