---
title: _com_error::GUID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f63d81fa8550bd9cbb7c051803c0d1e891cefe15
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031065"
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