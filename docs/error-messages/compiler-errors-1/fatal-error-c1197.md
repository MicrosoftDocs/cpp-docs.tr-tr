---
title: Önemli hata C1197 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dacd459729161cf635287697a4a6d35c15eab3e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227286"
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