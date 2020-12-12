---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: HelpContext'
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: 757fb572d9e41486af419712eb7f70cd7cfa7b14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295945"
---
# <a name="_com_errorhelpcontext"></a>_com_error::HelpContext

**Microsoft'a Özgü**

Çağıran `IErrorInfo::GetHelpContext` işlevi.

## <a name="syntax"></a>Syntax

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

`IErrorInfo::GetHelpContext` `IErrorInfo` Nesne içinde kaydedilen nesnenin sonucunu döndürür `_com_error` . Hiçbir `IErrorInfo` nesne kaydediltiyse, sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

Yöntemi çağırırken herhangi bir hata `IErrorInfo::GetHelpContext` yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error sınıfı](../cpp/com-error-class.md)
