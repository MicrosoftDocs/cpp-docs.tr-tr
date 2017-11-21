---
title: "Bağlayıcı araçları hatası LNK2011 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2011
dev_langs: C++
helpviewer_keywords: LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a660356f719003a06c17d1fddba948e9d903e00a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2011"></a>Bağlayıcı Araçları Hatası LNK2011
önceden derlenmiş nesnesi bağlı değil; Görüntü çalışmayabilir  
  
 Önceden derlenmiş üstbilgiler kullanırsanız, önceden derlenmiş üst bilgileri ile oluşturulan tüm nesne dosyaların içinde bağlanmalıdır bağlantı gerektirir. Diğer kaynak dosyaları ile kullanım için önceden derlenmiş üstbilgi oluşturmak için kullandığınız kaynak dosyası varsa, önceden derlenmiş üst bilgi ile birlikte oluşturulan nesne dosyası artık eklemeniz gerekir.  
  
 Örneğin, diğer kaynak dosyalarını içeren kullanmak için önceden derlenmiş üstbilgi oluşturmak için STUB.cpp adlı bir dosya derleme yaparsanız STUB.obj ile bağlamanız gerekir veya bu hatayı alırsınız. Aşağıdaki komut satırları, bir satırı PROG1.cpp ve PROG2.cpp ikinci ve üçüncü satırlarında kullanılır COMMON.pch önceden derlenmiş üst bilgi oluşturmak için kullanılır. STUB.cpp içeren yalnızca dosyanın `#include` satırları (aynı `#include` satırları PROG1.cpp ve PROG2.cpp olduğu gibi) ve yalnızca önceden derlenmiş üst bilgileri oluşturmak için kullanılır. Son satırında STUB.obj içinde LNK2011 önlemek için bağlı olması gerekir.  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```