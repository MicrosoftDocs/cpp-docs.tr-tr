---
title: "Derleyici Hatası C2070 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2070
dev_langs: C++
helpviewer_keywords: C2070
ms.assetid: 4c8dea63-1227-4aba-be26-2462537f86fb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0923caf84c3980c4ee1b4eaa832752f34a447cc1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2070"></a>Derleyici Hatası C2070
'type': Geçersiz sizeof işleneni  
  
 [Sizeof](../../cpp/sizeof-operator.md) işleci bir deyim veya türü adı gerektirir.  
  
 Aşağıdaki örnek C2070 oluşturur:  
  
```  
// C2070.cpp  
void func() {}  
int main() {  
   int a;  
   a = sizeof(func);   // C2070  
}  
```  
  
 Olası çözüm:  
  
```  
// C2070b.cpp  
void func() {}  
int main() {  
   int a;  
   a = sizeof(a);  
}  
```