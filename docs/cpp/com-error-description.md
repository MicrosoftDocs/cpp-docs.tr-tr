---
title: _com_error::Description | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90208866ee08d6990d8f1b5322a38fbd2d63a651
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091796"
---
# <a name="comerrordescription"></a>_com_error::Description

**Microsoft'a özgü**

Çağrıları `IErrorInfo::GetDescription` işlevi.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>Dönüş Değeri

Sonucunu döndürür `IErrorInfo::GetDescription` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Ortaya çıkan `BSTR` içinde kapsüllenir bir `_bstr_t` nesne. Hayır ise `IErrorInfo` olan kaydedilmemişse, boş bir döndürür `_bstr_t`.

## <a name="remarks"></a>Açıklamalar

Çağrıları `IErrorInfo::GetDescription` işlevi ve alır `IErrorInfo` içinde kaydedilen `_com_error` nesne. Çağrılırken `IErrorInfo::GetDescription` yöntemi göz ardı edilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)