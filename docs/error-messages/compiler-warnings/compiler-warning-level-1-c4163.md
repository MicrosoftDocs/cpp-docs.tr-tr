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
ms.openlocfilehash: 91e8ac4b7e16a589ba15476414b5ae2f795d04e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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