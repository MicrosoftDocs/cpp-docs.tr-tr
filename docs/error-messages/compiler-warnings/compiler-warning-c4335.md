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
ms.openlocfilehash: adb8a7b484ce0946f385c3b2a8669ba1b5ccf0d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4335"></a>Derleyici Uyarısı C4335
Mac dosya biçimi algılandı: Lütfen kaynak dosyasını DOS veya UNIX biçimine Dönüştür  
  
 Bir kaynak dosyasının ilk satırının satır sonlandırma karakteri UNIX ('\n') veya DOS ('\r\n') aksine Macintosh stili ('\r') ' dir.  
  
 Bu uyarı, bir hatası her zaman görüntülenir.  Bkz: [uyarı](../../preprocessor/warning.md) pragma bu uyarıyı devre dışı bırakma hakkında bilgi için.  Ayrıca, bu yalnızca bir kez derlenecek dosya uyarı görüntülenir. Bu nedenle, yoksa birden çok `#include` dosyaları Macintosh biçiminde belirtin yönergeleri, C4335 yalnızca verilir kez.  
  
 Macintosh biçiminde dosyaları oluşturmak için bir yoldur kullanarak **Gelişmiş kaydetme seçenekleri** (üzerinde **dosya** menüsü) Visual Studio.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4335 oluşturur.  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```