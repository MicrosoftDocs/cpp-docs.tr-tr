---
title: "Derleyici Hatası C2014 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2014
dev_langs: C++
helpviewer_keywords: C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a4c6a3cc07b28e5636e61769b6dce0760938c591
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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