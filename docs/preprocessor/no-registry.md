---
title: no_registry
ms.date: 10/18/2018
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: 2a0fd9a761f765aa9562ab18c095f683b80c7987
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023431"
---
# <a name="noregistry"></a>no_registry

**no_registry** derleyiciye tür kitaplıklarını içeri için kayıt defterini aranmayacak `#import`.

## <a name="syntax"></a>Sözdizimi

```
#import filename no_registry
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Bir tür kitaplığı.

## <a name="remarks"></a>Açıklamalar

Başvurulan tür kitaplığının dizinleri bulunmazsa, tür kitaplığının kayıt defterinde olsa bile, derleme başarısız olur.  **no_registry** için örtük olarak içeri diğer tür kitaplıklarında yayar `auto_search`.

Derleyici, hiçbir zaman doğrudan geçirilen ve dosya adıyla belirtilen tür kitaplıkları için kayıt defterini arar `#import`.

Zaman `auto_search` belirtilirse, ek `#import`s ile oluşturulacak **no_registry** ilk harfini ayarlama `#import` (durumunda ilk `#import` yönergesi olduğu **no_registry** e `auto_search`-oluşturulan `#import` de **no_registry**.)

**no_registry** çapraz başvurulan tür kitaplıkları dosyanın daha eski bir sürümünü kayıt defterinde bulma derleyici riski olmadan içeri aktarmak istediğiniz durumlarda kullanışlıdır. **no_registry** tür kitaplığı kayıtlı değil de kullanışlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[#import Öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Yönergesi](../preprocessor/hash-import-directive-cpp.md)