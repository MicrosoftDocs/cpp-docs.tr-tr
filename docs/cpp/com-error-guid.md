---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: GUID'
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: 32f88728d5c0f93094413aaeae8fb3c116b415c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295971"
---
# <a name="_com_errorguid"></a>_com_error::GUID

**Microsoft'a Özgü**

Çağıran `IErrorInfo::GetGUID` işlevi.

## <a name="syntax"></a>Syntax

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

`IErrorInfo::GetGUID` `IErrorInfo` Nesne içinde kaydedilen nesnenin sonucunu döndürür `_com_error` . Hiçbir `IErrorInfo` nesne kaydediltiyse, döndürür `GUID_NULL` .

## <a name="remarks"></a>Açıklamalar

Yöntemi çağırırken herhangi bir hata `IErrorInfo::GetGUID` yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error sınıfı](../cpp/com-error-class.md)
