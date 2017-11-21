---
title: "Derleyici Hatası C3254 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3254
dev_langs: C++
helpviewer_keywords: C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 104ee89c45d8a1134611535ab6aa9c62f09e139c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3254"></a>Derleyici Hatası C3254
'açık geçersiz kılma': sınıf açık geçersiz kılma 'override' içeriyor, ancak işlev bildirimi içeren bir arabirimi türevi değildir  
  
 Olduğunda, [açıkça geçersiz](../../cpp/explicit-overrides-cpp.md) işlevi içeren türü, geçersiz kılma, bir yöntemi geçersiz kılma içeren sınıf, doğrudan veya dolaylı olarak türetilmesi gerekir.  
  
 Aşağıdaki örnek C3254 oluşturur:  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```