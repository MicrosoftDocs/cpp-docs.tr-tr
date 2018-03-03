---
title: "Önemli hata C1197 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1658e55a9298df703051b856bb9b10dd02d8cc68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1197"></a>Önemli hata C1197
program zaten 'mscorlib.dll_2' başvurmuş gibi 'mscorlib.dll_1' başvuramaz.  
  
 Ortak dil çalışma zamanı sürümüne derleyici eşleşir.  Ancak, bir önceki bir sürümden bir ortak dil çalışma zamanı dosyası sürümünü başvurmak için girişimde bulunuldu.  
  
 Bu hatayı gidermek için yalnızca Visual C++ ile derleme sürümü ile birlikte gelen ortak dil çalışma zamanı sürümünden dosyaları başvuru.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C1197 oluşturur:  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```