---
title: include()
ms.date: 10/18/2018
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: 1208f14a9f6b3724dd5353df57213baa3910d07f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383743"
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

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)