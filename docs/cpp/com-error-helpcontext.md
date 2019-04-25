---
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: a421a7fd7fa0817c74dac66946e28928b2ad82dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155091"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext

**Microsoft'a özgü**

Çağrıları `IErrorInfo::GetHelpContext` işlevi.

## <a name="syntax"></a>Sözdizimi

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

Sonucunu döndürür `IErrorInfo::GetHelpContext` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Hayır ise `IErrorInfo` nesnesi kaydedilmezse, sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

Çağrılırken `IErrorInfo::GetHelpContext` yöntemi göz ardı edilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)