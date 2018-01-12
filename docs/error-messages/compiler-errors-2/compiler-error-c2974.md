---
title: "Derleyici Hatası C2974 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2974
dev_langs: C++
helpviewer_keywords: C2974
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84a5d4d239df7b495c4b65341f0e3574c15fae73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2974"></a>Derleyici Hatası C2974
geçersiz tür bağımsız değişkeni 'number', beklenen türü  
  
 Genel veya şablon bağımsız değişkeni genel veya şablon bildirimi eşleşmiyor. Bir tür açılı ayraçları içinde görünmesi gerekir. Doğru türlerini bulmak için genel veya şablon tanımını denetleyin.  
  
 Aşağıdaki örnek C2974 oluşturur:  
  
```  
// C2974.cpp  
// C2974 expected  
template <class T>  
struct TC {};  
  
template <typename T>  
void tf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   TC<1>* tc;  
   tf<"abc">("abc");  
  
   TC<int>* tc;  
   tf<const char *>("abc");  
}  
```  
  
 Ayrıca C2974 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2974b.cpp  
// compile with: /clr  
// C2974 expected  
using namespace System;  
generic <class T>  
ref struct GCtype {};  
  
generic <typename T>  
void gf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   GCtype<"a">^ gc;  
   gf<"a">("abc");  
  
   // OK  
   GCtype<int>^ gc;  
   gf<String ^>("abc");  
}  
```