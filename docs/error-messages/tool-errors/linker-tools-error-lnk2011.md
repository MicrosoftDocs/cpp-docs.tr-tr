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
ms.workload: cplusplus
ms.openlocfilehash: 9811bdb905df61bb77ea4af6bc4ced7c4ba42106
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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