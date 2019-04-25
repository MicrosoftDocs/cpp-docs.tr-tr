---
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 8856289605cce430fdab36d6e3e8b743190e02ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155130"
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