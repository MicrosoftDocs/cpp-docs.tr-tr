---
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: 905b67577a65b81be0b4d18c7513652dd8c5f055
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661636"
---
# <a name="comerrorguid"></a>_com_error::GUID

**Microsoft'a özgü**

Çağrıları `IErrorInfo::GetGUID` işlevi.

## <a name="syntax"></a>Sözdizimi

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

Sonucunu döndürür `IErrorInfo::GetGUID` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Hayır ise `IErrorInfo` nesnesi kaydedilmezse döndürür `GUID_NULL`.

## <a name="remarks"></a>Açıklamalar

Çağrılırken `IErrorInfo::GetGUID` yöntemi göz ardı edilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)