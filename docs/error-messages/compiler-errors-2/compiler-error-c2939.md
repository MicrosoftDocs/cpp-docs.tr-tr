---
title: "Derleyici Hatası C2939 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2939
dev_langs: C++
helpviewer_keywords: C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 881d5148a2c1ee5279c85c4673493438093ca7a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2939"></a>Derleyici Hatası C2939
'class': türü sınıfı kimliği yerel veri değişken olarak yeniden tanımlandı  
  
 Yerel veri değişkeni olarak bir genel veya Şablon sınıfı kullanamazsınız.  
  
 Küme ayraçları yanlış eşleşirse bu hataya neden olabilir.  
  
 Aşağıdaki örnek C2939 oluşturur:  
  
```  
// C2939.cpp  
template<class T>  
struct TC { };   
int main() {  
   int TC<int>;   // C2939  
   int TC;   // OK  
}  
```  
  
 Ayrıca C2939 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2939b.cpp  
// compile with: /clr  
generic<class T>  
ref struct GC { };  
  
int main() {  
   int GC<int>;   // C2939  
   int GC;   // OK  
}  
```