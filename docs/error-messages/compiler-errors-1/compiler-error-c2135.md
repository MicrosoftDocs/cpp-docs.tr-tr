---
title: "Derleyici Hatası C2135 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2135
dev_langs: C++
helpviewer_keywords: C2135
ms.assetid: aa360d22-4f79-4de1-b384-93cadd10975f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e520918edc1534f1bd6f0af89ab8accf377b2587
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2135"></a>Derleyici Hatası C2135
'bit işleci': geçersiz bit alan işlemi  
  
 Address-of işleci (`&`) bir bit alana uygulanamaz.  
  
 Aşağıdaki örnek C2135 oluşturur:  
  
```  
// C2135.cpp  
struct S {  
   int i : 1;  
};  
  
struct T {  
   int j;  
};  
int main() {  
   &S::i;   // C2135 address of a bit field  
   &T::j;   // OK  
}  
```