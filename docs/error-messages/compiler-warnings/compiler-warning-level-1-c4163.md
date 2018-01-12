---
title: "Derleyici Uyarısı (düzey 1) C4163 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4163
dev_langs: C++
helpviewer_keywords: C4163
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6eb19f9b848268835d7fbb42f8cf1548f08853c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4163"></a>Derleyici Uyarısı (düzey 1) C4163
'tanımlayıcısı': iç bir işlevi olarak mevcut değil  
  
 Belirtilen işlev olarak kullanılamaz bir [iç](../../preprocessor/intrinsic.md) işlevi. Derleyici geçersiz işlev adı yok sayar.  
  
 Aşağıdaki örnek C4163 oluşturur:  
  
```  
// C4163.cpp  
// compile with: /W1 /LD  
#include <math.h>  
#pragma intrinsic(mysin)   // C4163  
// try the following line instead  
// #pragma intrinsic(sin)  
```