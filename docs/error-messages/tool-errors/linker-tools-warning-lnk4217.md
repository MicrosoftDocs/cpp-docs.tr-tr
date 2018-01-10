---
title: "Bağlayıcı araçları uyarısı LNK4217 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4217
dev_langs: C++
helpviewer_keywords: LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09c984d7675c73bdf225bae7d3014f81153d20e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4217"></a>Bağlayıcı Araçları Uyarısı LNK4217
yerel olarak simgesi 'simgesi işlevi 'function' alındı' tanımlandı  
  
 [__declspec(dllimport)](../../cpp/dllexport-dllimport.md) simgenin yerel olarak tanımlanan olsa bile bir simge için belirtildi. Kaldırma `__declspec` bu uyarıyı çözümlemek için değiştiricisi.  
  
 `symbol`içindeki görüntü tanımlanmış sembol adıdır. `function`simgenin alma işlevdir.  
  
 Bu uyarı seçeneğini kullanarak derlediğinizde görünmez [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 İlk modülü içeri aktarma kitaplığını sahip ikinci modül yerine derleme yaparken iki modülleri birlikte, bağlantı girişimi LNK4217 de ortaya çıkabilir.  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 Ardından,  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 Bu iki modülleri bağlantı girişimi içinde LNK4217 neden, ikinci örneği çözümlemek için ilk örnek içeri aktarma kitaplığı ile derleyin.