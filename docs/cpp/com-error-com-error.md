---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: _com_error'
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 2c5b912f5d532e9aed5b8e84a3fe7e2fcd7d4100
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332560"
---
# <a name="_com_error_com_error"></a>_com_error::_com_error

**Microsoft'a Özgü**

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

*sa*<br/>
HRESULT bilgileri.

*perrınfo*<br/>
`IErrorInfo` nesne.

*fAddRef*<br/>
Varsayılan değer, oluşturucunun null olmayan bir arabirimde AddRef 'yi çağırmasını sağlar `IErrorInfo` . Bu, arabirimin sahipliğinin **_com_error** nesnesine geçirildiği ortak durumda doğru başvuru sayımı sağlar; örneğin:

```cpp
throw _com_error(hr, perrinfo);
```

Kodunuzun **_com_error** nesnesine sahiplik aktarmasını istemiyorsanız ve `AddRef` `Release` **_com_error** yıkıcısında kaydırılacağı için, nesneyi aşağıdaki gibi oluşturun:

```cpp
_com_error err(hr, perrinfo, true);
```

*öneririz*<br/>
Var olan bir **_com_error** nesnesi.

## <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, HRESULT ve isteğe bağlı nesne verilen yeni bir nesne oluşturur `IErrorInfo` . İkincisi, varolan bir **_com_error** nesnesinin bir kopyasını oluşturur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error sınıfı](../cpp/com-error-class.md)
