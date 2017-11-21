---
title: "Derleyici Hatası C3350 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3350
dev_langs: C++
helpviewer_keywords: C3350
ms.assetid: cfbbc338-92b5-4f34-999e-aa2d2376bc70
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ec6d0823fe29b51a002f6c46f728f0c526c6169
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3350"></a>Derleyici Hatası C3350
'temsilci': sayı bağımsız değişkenli bir temsilci Oluşturucu bekliyor  
  
 Bir temsilci örneği oluşturduğunuzda, iki bağımsız değişkeni, temsilci işlevi ve işlevi içeren türünün bir örneği geçmesi gerekir.  
  
 Aşağıdaki örnek C3350 oluşturur:  
  
```  
// C3350.cpp  
// compile with: /clr  
delegate void SumDelegate();  
  
public ref class X {  
public:  
   void F() {}  
   static void F2() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   SumDelegate ^ pSD = gcnew SumDelegate();   // C3350  
   SumDelegate ^ pSD1 = gcnew SumDelegate(MyX, &X::F);  
   SumDelegate ^ pSD2 = gcnew SumDelegate(&X::F2);  
}  
```  
