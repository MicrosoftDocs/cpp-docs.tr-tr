---
title: no_implementation
ms.date: 11/04/2016
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: d4e55d06bef823d28c5deb3467654bc530a3853e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456790"
---
# <a name="noimplementation"></a>no_implementation
**C++ özgü**

Kapsayıcı üye işlevleri uygulamalarını içeren .tli başlık oluşturulmasını bastırır.

## <a name="syntax"></a>Sözdizimi

```
no_implementation
```

## <a name="remarks"></a>Açıklamalar

Bu öznitelik belirtilmezse, .tlh üstbilgiyle türü kitaplık öğelerini göstermek için bildirimleri olmadan oluşturulan bir `#include` deyimini .tli üstbilgi dosyasını dahil edin.

Bu öznitelik ile birlikte kullanılan [implementation_only](../preprocessor/implementation-only.md).

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)