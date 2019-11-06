---
title: Derleyici Uyarısı C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: ccb00118d0c6895eee84976bb01472ea2f98353d
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627130"
---
# <a name="compiler-warning-c4335"></a>Derleyici Uyarısı C4335

Mac dosya biçimi algılandı: lütfen kaynak dosyayı DOS veya UNIX biçimine dönüştürün

Kaynak dosyanın ilk satırının satır sonlandırma karakteri, UNIX (' \n ') veya DOS (' \r\n ') aksine Macintosh stili (' \r ').

Bu uyarı her zaman bir hata olarak verilir.  Bu uyarıyı devre dışı bırakma hakkında bilgi için bkz. [Warning](../../preprocessor/warning.md) pragma.  Ayrıca, bu uyarı compiland başına yalnızca bir kez verilir. Bu nedenle, Macintosh biçiminde dosyaları belirten birden çok `#include` yönergesi varsa, C4335 yalnızca bir kez verilir.

Macintosh biçiminde dosya oluşturmanın bir yolu, Visual Studio 'daki **Gelişmiş Kaydet seçeneklerini** ( **Dosya** menüsünde) kullanmaktır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4335 oluşturur.

```cpp
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```
