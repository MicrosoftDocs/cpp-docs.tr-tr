---
description: 'Daha fazla bilgi edinin: saplama'
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: 79a2002c119bf211652e2aab51d9656b36e3d159
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230295"
---
# <a name="stub"></a>STUB

Bir sanal cihaz sürücüsü (VxD) oluşturan bir modül tanımı dosyasında kullanıldığında, IMAGE_DOS_HEADER yapısını içeren bir dosya adı belirtmenize olanak tanır (WINNT içinde tanımlanmıştır). H) varsayılan üst bilgi yerine sanal cihaz sürücüsünde (VxD) kullanılacak.

```
STUB:filename
```

## <a name="remarks"></a>Açıklamalar

*Dosya adını* belirtmenin eşdeğer bir yolu, [/Stub](stub-ms-dos-stub-file-name.md) bağlayıcı seçeneğidir.

SAPLAMA yalnızca bir VxD oluşturulurken modül tanımı dosyasında geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Module-Definition deyimleri için kurallar](rules-for-module-definition-statements.md)
