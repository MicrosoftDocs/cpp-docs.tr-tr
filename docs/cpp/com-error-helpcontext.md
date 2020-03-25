---
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: b3c79bb069ef504680e83359d6ec90c803f16d9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180595"
---
# <a name="_com_errorhelpcontext"></a>_com_error::HelpContext

**Microsoft 'a özgü**

`IErrorInfo::GetHelpContext` işlevini çağırır.

## <a name="syntax"></a>Sözdizimi

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

`_com_error` nesnesi içinde kaydedilen `IErrorInfo` nesnesi için `IErrorInfo::GetHelpContext` sonucunu döndürür. `IErrorInfo` nesne kaydedilmez, sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

`IErrorInfo::GetHelpContext` yöntemi çağrılırken herhangi bir hata yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)
