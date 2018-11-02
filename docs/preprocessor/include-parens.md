---
title: include()
ms.date: 10/18/2018
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: 8f3227ba49cc0928fec5d5917efcd8869982d94a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599751"
---
# <a name="include"></a>include()

**C++ özgü**

Otomatik dışlama devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

```
include("Name1"[,"Name2", ...])
```

### <a name="parameters"></a>Parametreler

*Name1*<br/>
Zorla dahil edilecek ilk öğe.

*Name2*<br/>
(Gerekirse) zorla dahil edilecek ikinci öğe.

## <a name="remarks"></a>Açıklamalar

Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. `#import` otomatik olarak gibi öğeler hariç tutarak birden çok tanım hatalarını önlemek çalışır. Öğeleri, gösterildiği gibi tutulan varsa [Derleyici Uyarısı (Düzey 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), ve bunlar olmaması gereken olup, bu öznitelik, otomatik dışlama devre dışı bırakmak için kullanılabilir. Bu öznitelik her dahil edilmek üzere tür kitaplığı öğesi adı olan herhangi bir sayıda bağımsız değişken alabilir.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)