---
title: no_implementation
ms.date: 11/04/2016
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 26527ca69c66c73f5d41084dc42df5faa34481d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409817"
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

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)