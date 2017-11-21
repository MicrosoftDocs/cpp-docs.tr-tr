---
title: "Derleyici Hatası C3866 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3866
dev_langs: C++
helpviewer_keywords: C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b1bcba6226a05379248a68f2047653333d98cdf8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3866"></a>Derleyici Hatası C3866
işlev çağrısı eksik bağımsız değişken listesi  
  
 Statik olmayan üye fonksiyonu içinde yıkıcı veya sonlandırıcıyı çağrısı bir bağımsız değişken listesi sahip değil.  
  
 Aşağıdaki örnek C3866 oluşturur:  
  
```  
// C3866.cpp  
// compile with: /c  
class C {  
   ~C();  
   void f() {  
      this->~C;   // C3866  
      this->~C();   // OK  
   }  
};  
```