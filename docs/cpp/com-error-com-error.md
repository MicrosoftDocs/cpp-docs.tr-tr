---
title: _com_error::_com_error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89377e33e56b0796fc850c050c8e79eac86ee07d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040472"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error

**Microsoft'a özgü**

Oluşturur bir **_com_error** nesne.

## <a name="syntax"></a>Sözdizimi

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>Parametreler

*İK*<br/>
HRESULT bilgileri.

*perrinfo*<br/>
`IErrorInfo` nesne.

*fAddRef*<br/>
Varsayılan null olmayan bir üzerinde AddRef çağırmasına neden `IErrorInfo` arabirimi. Bu doğru başvuru sayımı burada sahipliğini arabiriminin geçirilen içine ortak durumda sağlayan **_com_error** gibi nesnesi:

```cpp
throw _com_error(hr, perrinfo);
```

Kodunuzun sahipliği istemiyorsanız **_com_error** nesnesi ve `AddRef` yıkıcısında `Release` içinde **_com_error** yıkıcı nesnesi olarak oluşturun aşağıdaki gibidir:

```cpp
_com_error err(hr, perrinfo, true);
```

*,*<br/>
Mevcut bir **_com_error** nesne.

## <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir HRESULT ve isteğe bağlı verilen yeni bir nesne oluşturur `IErrorInfo` nesne. İkincisi, varolan bir kopyasını oluşturur **_com_error** nesne.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)