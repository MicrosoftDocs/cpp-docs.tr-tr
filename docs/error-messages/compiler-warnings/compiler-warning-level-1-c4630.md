---
title: "Derleyici Uyarısı (düzey 1) C4630 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4630
dev_langs: C++
helpviewer_keywords: C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 93d6bd976876f8abea6a0caf33fcd47860b19682
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4630"></a>Derleyici Uyarısı (düzey 1) C4630
'simgesi': 'extern' depolama sınıfı tanımlayıcısı üye tanımı geçersiz  
  
 Veri üyesi veya üye fonksiyonu olarak tanımlanır `extern`. Tüm nesneler; ancak üyeleri dış, olamaz. Derleyici yoksayar `extern` anahtar sözcüğü. Aşağıdaki örnek C4630 oluşturur:  
  
```  
// C4630.cpp  
// compile with: /W1 /LD  
class A {  
   void func();  
};  
  
extern void A::func() {   // C4630, remove 'extern' to resolve  
}  
```