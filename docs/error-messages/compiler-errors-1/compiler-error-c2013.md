---
title: "Derleyici Hatası C2013 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2013
dev_langs: C++
helpviewer_keywords: C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 23fdceda3b40a657301e8909c6847e9d596eb24d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2013"></a>Derleyici Hatası C2013
eksik ' >'  
  
 Bir `#include` yönergesi kapanış açılı ayracı eksik. Hatayı gidermek için kapanış ayracı ekleyin.  
  
 Aşağıdaki örnek C2013 oluşturur:  
  
```  
// C2013.cpp  
#include <stdio.h    // C2013  
```  
  
 Olası çözüm:  
  
```  
// C2013b.cpp  
// compile with: /c  
#include <stdio.h>  
```