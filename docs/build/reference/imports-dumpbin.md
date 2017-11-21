---
title: -IMPORTS (DUMPBIN) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /imports
dev_langs: C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e395896c7f595780b1bb6b667d53d4e3eb5fa2ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)
```  
/IMPORTS[:file]  
```  
  
 Bu seçenek DLL'lerin listesini görüntüler (her ikisi de statik olarak bağlı ve [yüklenen gecikme](../../build/reference/linker-support-for-delay-loaded-dlls.md)), alma işlemi yürütülebilir bir dosyanın veya DLL ve tek tek tüm içe aktarmaları için her bu DLL'ler.  
  
 İsteğe bağlı `file` belirtimi içeri aktarmalar yalnızca bu DLL için görüntülenir belirtmenize olanak verir. Örneğin:  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçeneği tarafından görüntülenen çıktı benzer [/EXPORTS](../../build/reference/dash-exports.md) çıktı.  
  
 Yalnızca [/HEADERS](../../build/reference/headers.md) DUMPBIN seçeneği ile üretilen dosyalarda kullanıma [/GL](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DUMPBIN seçenekleri](../../build/reference/dumpbin-options.md)