---
title: Derleyici Uyarısı C4335 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2b28909d0c4b663fffeacbec58ad694131bb008
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036585"
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