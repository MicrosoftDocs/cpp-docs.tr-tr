---
title: "Derleyici Hatası C2019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2019
dev_langs: C++
helpviewer_keywords: C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 93c91bccf1b9bc709d006696b22e0e8c2febb713
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2019"></a>Derleyici Hatası C2019
Beklenen önişlemci yönergesi bulundu 'karakter'  
  
 Karakter ve ardından bir `#` oturum ancak değil önişlemci yönergesi ilk harfini.  
  
 Aşağıdaki örnek C2019 oluşturur:  
  
```  
// C2019.cpp  
#!define TRUE 1   // C2019  
```  
  
 Olası çözüm:  
  
```  
// C2019b.cpp  
// compile with: /c  
#define TRUE 1  
```