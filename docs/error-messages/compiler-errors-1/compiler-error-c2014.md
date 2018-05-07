---
title: Derleyici Hatası C2014 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2014
dev_langs:
- C++
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 839fececb10897c799473ae328afb9f422b4c390
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2014"></a>Derleyici Hatası C2014
Önişlemci komutu ilk renkleri alan olarak başlamalıdır  
  
 `#` Önişlemci yönergesi belirtisi ilk karakteri boşluk olmayan bir satırda olmalıdır.  
  
 Aşağıdaki örnek C2014 oluşturur:  
  
```  
// C2014.cpp  
int k; #include <stdio.h>   // C2014  
```  
  
 Olası çözüm:  
  
```  
// C2014b.cpp  
// compile with: /c  
int k;   
#include <stdio.h>  
```