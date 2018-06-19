---
title: -IMPORTS (DUMPBIN) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /imports
dev_langs:
- C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af3b9a1bbcf1769e87715e46566dee9c53a96747
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373445"
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
 [DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)