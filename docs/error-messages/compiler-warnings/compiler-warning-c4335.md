---
title: Derleyici Uyarısı C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: d44a1ae5354e8d22e41694f4d6df42ad22c3986d
ms.sourcegitcommit: 76cc69b482ada8ebf0837e8cdfd4459661f996dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71127159"
---
# <a name="compiler-warning-c4335"></a>Derleyici Uyarısı C4335

Mac dosya biçimi algılandı: lütfen kaynak dosyayı DOS veya UNIX biçimine dönüştürün

Kaynak dosyanın ilk satırının satır sonlandırma karakteri, UNIX (' \n ') veya DOS (' \r\n ') aksine Macintosh stili (' \r ').

Bu uyarı her zaman bir hata olarak verilir.  Bu uyarıyı devre dışı bırakma hakkında bilgi için bkz. [Warning](../../preprocessor/warning.md) pragma.  Ayrıca, bu uyarı compiland başına yalnızca bir kez verilir. Bu nedenle, Macintosh biçiminde dosyaları `#include` belirten birden fazla yönergeler varsa, C4335 yalnızca bir kez verilir.

Macintosh biçiminde dosya oluşturmanın bir yolu, Visual Studio 'daki **Gelişmiş Kaydet seçeneklerini** ( **Dosya** menüsünde) kullanmaktır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4335 oluşturur.

```
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```
