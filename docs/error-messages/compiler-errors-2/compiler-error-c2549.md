---
title: "Derleyici Hatası C2549 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2549
dev_langs: C++
helpviewer_keywords: C2549
ms.assetid: 29310094-54a3-4605-bc6d-a312a68daf5d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5e5ed175c46566cfab5dc235c664880817ede3a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2549"></a>Derleyici Hatası C2549
Kullanıcı tanımlı dönüştürme dönüş türü belirtilemez  
  
 Aşağıdaki örnek C2549 oluşturur:  
  
```  
// C2549.cpp  
// compile with: /c  
class X {  
public:  
   int operator int() { return value; }   // C2549  
  
   // try the following line instead  
   // operator int() { return value; }  
private:  
   int value;  
};  
```