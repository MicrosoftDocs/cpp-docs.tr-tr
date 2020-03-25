---
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 4ac902f0fda90f77526ef53139ef0d523d8c22e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180790"
---
# <a name="_com_error_com_error"></a>_com_error::_com_error

**Microsoft 'a özgü**

**_Com_error** nesnesi oluşturur.

## <a name="syntax"></a>Sözdizimi

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>Parametreler

*HR*<br/>
HRESULT bilgileri.

*perrınfo*<br/>
`IErrorInfo` nesnesi.

*fAddRef*<br/>
Varsayılan değer, oluşturucunun null olmayan bir `IErrorInfo` arabiriminde AddRef 'yi çağırmasını sağlar. Bu, arabirimin sahipliğinin **_com_error** nesnesine geçirildiği ortak durumda doğru başvuru sayımı sağlar; örneğin:

```cpp
throw _com_error(hr, perrinfo);
```

Kodunuzun **_com_error** nesnesine sahiplik aktarmasını istemiyorsanız ve `AddRef`, **_com_error** yıkıcısında `Release` kaydırmak için gerekliyse, nesneyi aşağıdaki gibi oluşturun:

```cpp
_com_error err(hr, perrinfo, true);
```

*öneririz*<br/>
Var olan bir **_com_error** nesnesi.

## <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, HRESULT ve isteğe bağlı `IErrorInfo` nesnesi verilen yeni bir nesne oluşturur. İkincisi, varolan bir **_com_error** nesnesinin bir kopyasını oluşturur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)
