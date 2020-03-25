---
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: d5b05cd4e26f89d42ea23b605f5e6560795a0cfa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180647"
---
# <a name="_com_errorguid"></a>_com_error::GUID

**Microsoft 'a özgü**

`IErrorInfo::GetGUID` işlevini çağırır.

## <a name="syntax"></a>Sözdizimi

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

`_com_error` nesnesi içinde kaydedilen `IErrorInfo` nesnesi için `IErrorInfo::GetGUID` sonucunu döndürür. `IErrorInfo` nesne kaydedilmez, `GUID_NULL`döndürür.

## <a name="remarks"></a>Açıklamalar

`IErrorInfo::GetGUID` yöntemi çağrılırken herhangi bir hata yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)
