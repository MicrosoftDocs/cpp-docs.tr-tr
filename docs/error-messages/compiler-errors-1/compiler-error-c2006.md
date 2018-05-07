---
title: Derleyici Hatası C2006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93880e7d767de3101cd7a292af5fa2874cae86bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2006"></a>Derleyici Hatası C2006
'belirteci' bulunan bir dosya adı 'yönergesi' bekleniyor  
  
 Yönergeleri gibi [#include](../../preprocessor/hash-include-directive-c-cpp.md) veya [#import](../../preprocessor/hash-import-directive-cpp.md) bir dosya adı gerektirir. Hatayı gidermek için emin *belirteci* geçerli bir dosya adı. Ayrıca, dosya adı çift tırnak işareti veya köşeli yerleştirin.  
  
 Aşağıdaki örnek C2006 oluşturur:  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 Olası çözüm:  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```