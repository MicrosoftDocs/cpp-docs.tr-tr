---
title: Bağlayıcı araçları hatası LNK2011 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2011
dev_langs:
- C++
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f60dce4cb260c670f5ee82aa88b9f106f3f14e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300761"
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