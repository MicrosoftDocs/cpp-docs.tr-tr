---
title: "Derleyici Uyarısı C4335 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4335
dev_langs: C++
helpviewer_keywords: C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ab7406a9c161d47e431cb0af8183d99eac7bfe86
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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