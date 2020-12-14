---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4335'
title: Derleyici Uyarısı C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: fc8f86036a299c41bc0cb1814b98372edc3b4d8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238316"
---
# <a name="compiler-warning-c4335"></a>Derleyici Uyarısı C4335

Mac dosya biçimi algılandı: lütfen kaynak dosyayı DOS veya UNIX biçimine dönüştürün

Kaynak dosyanın ilk satırının satır sonlandırma karakteri, UNIX (' \n ') veya DOS (' \r\n ') aksine Macintosh stili (' \r ').

Bu uyarı her zaman bir hata olarak verilir.  Bu uyarıyı devre dışı bırakma hakkında bilgi için bkz. [Warning](../../preprocessor/warning.md) pragma.  Ayrıca, bu uyarı compiland başına yalnızca bir kez verilir. Bu nedenle, `#include` Macintosh biçiminde dosyaları belirten birden fazla yönergeler varsa, C4335 yalnızca bir kez verilir.

Macintosh biçiminde dosya oluşturmanın bir yolu, Visual Studio 'daki **Gelişmiş Kaydet seçeneklerini** ( **Dosya** menüsünde) kullanmaktır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4335 oluşturur.

```cpp
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```
