---
description: 'Hakkında daha fazla bilgi edinin: _com_error::D escription'
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: 6404d16361abe81d9e234a6b63039a7476d91ef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332547"
---
# <a name="_com_errordescription"></a>_com_error::Description

**Microsoft'a Özgü**

Çağıran `IErrorInfo::GetDescription` işlevi.

## <a name="syntax"></a>Syntax

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>Dönüş Değeri

`IErrorInfo::GetDescription` `IErrorInfo` Nesne içinde kaydedilen nesnenin sonucunu döndürür `_com_error` . Sonuç `BSTR` olarak bir nesne içinde kapsüllenir `_bstr_t` . Hiçbiri `IErrorInfo` kayıtlı değilse, boş döndürür `_bstr_t` .

## <a name="remarks"></a>Açıklamalar

İşlevini çağırır `IErrorInfo::GetDescription` ve `IErrorInfo` nesne içinde kaydedilmiş alır `_com_error` . Yöntemi çağırırken herhangi bir hata `IErrorInfo::GetDescription` yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error sınıfı](../cpp/com-error-class.md)
