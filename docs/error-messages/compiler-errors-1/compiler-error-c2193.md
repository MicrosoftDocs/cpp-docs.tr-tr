---
title: "Derleyici Hatası C2193 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2193
dev_langs: C++
helpviewer_keywords: C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cad3fdb23a8aa5b9c929e533547b2c33f07dd79e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2193"></a>Derleyici Hatası C2193
'tanımlayıcısı': bir kesimdeki  
  
 Bir işlev kullanarak iki farklı segmentlerinde yerleştirilen `alloc_text` ve `code_seg` pragmaları.  
  
 Aşağıdaki örnek C2193 oluşturur:  
  
```  
// C2193.cpp  
// compile with: /c  
extern "C" void MYFUNCTION();  
#pragma alloc_text(MYCODE, MYFUNCTION)  
#pragma code_seg("MYCODE2")  
extern "C" void MYFUNCTION() {}   // C2193  
extern "C" void MYFUNCTION2() {}  
```