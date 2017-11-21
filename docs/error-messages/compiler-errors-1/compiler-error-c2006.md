---
title: "Derleyici Hatası C2006 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2006
dev_langs: C++
helpviewer_keywords: C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8d182e7a98d01dee4047defa5adb5ccc2dc7cde5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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