---
title: Derleyici Uyarısı C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: 43c2f5d9092cdbad14e429349bd7d04e236b75e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447287"
---
# <a name="compiler-warning-c4335"></a>Derleyici Uyarısı C4335

Mac dosya biçimi algılandı: Lütfen kaynak dosyayı DOS veya UNIX biçimine dönüştürün

Bir kaynak dosyasının ilk satırının satır sonlandırma karakteri UNIX ('\n') veya DOS ('\r\n') aksine Macintosh stili ('\r') ' dir.

Bu uyarı, bir hata her zaman görüntülenir.  Bkz: [uyarı](../../preprocessor/warning.md) pragma bu uyarıyı devre dışı bırakma hakkında daha fazla bilgi için.  Ayrıca, bu uyarı yalnızca bir kez derlenecek görüntülenir. Bu nedenle, varsa birden çok `#include` Macintosh biçiminde dosyaları belirttiğiniz yönergeleri C4335 yalnızca gönderilmez kez.

Macintosh biçiminde dosyaları oluşturmak için bir yoludur kullanarak **Gelişmiş kaydetme seçenekleri** (üzerinde **dosya** menüsü) Visual Studio'da.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4335 oluşturur.

```
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```