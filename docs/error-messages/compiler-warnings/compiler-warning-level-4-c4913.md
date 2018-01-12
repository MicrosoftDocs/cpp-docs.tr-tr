---
title: "Derleyici Uyarısı (düzey 4) C4913 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4913
dev_langs: C++
helpviewer_keywords: C4913
ms.assetid: b94aa52e-6029-4170-9134-017714931546
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67f0d5d3c163c4e6bb85f298eb96203577e148b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4913"></a>Derleyici Uyarısı (düzey 4) C4913
**Kullanıcı tanımlı ikili işleç ',' var, ancak hiçbir aşırı yüklemesi dönüştüremedi tüm işlenenler, varsayılan yerleşik ikili işleç ',' kullanılan**  
  
 Bir çağrı yerleşik virgül işleci aşırı yüklenmiş virgül işleci de olan bir programı oluştu; bir düşünce oluşmuş olabilecek dönüştürme belirtmiyor.  
  
 Aşağıdaki kod örneği C4913 oluşturur:  
  
```  
// C4913.cpp  
// compile with: /W4  
struct A  
{  
};  
  
struct S  
{  
};  
  
struct B  
{  
   // B() { }  
   // B(S &s) { s; }  
};  
  
B operator , (A a, B b)     
{  
   a;  
   return b;  
}  
  
int main()  
{  
   A a;  
   B b;  
   S s;  
  
   a, b;   // OK calls user defined operator  
   a, s;   // C4913 uses builtin comma operator  
           // uncomment the conversion code in B to resolve.  
}  
```