---
title: include() | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- include()
dev_langs:
- C++
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b453daab9d140613587bb2d2857afdfa0a50c70
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808569"
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