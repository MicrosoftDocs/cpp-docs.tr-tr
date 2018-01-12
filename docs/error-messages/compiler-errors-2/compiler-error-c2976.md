---
title: "Derleyici Hatası C2976 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2976
dev_langs: C++
helpviewer_keywords: C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b398f89f2ff6816db22584f291eefa0d3abab324
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2976"></a>Derleyici Hatası C2976
'tanımlayıcısı': çok az tür bağımsız değişkenleri  
  
 Genel veya şablon bir veya daha fazla gerçek bağımsız değişkenler eksik. Doğru parametrelerin sayısı bulmak için genel ya da şablon bildirimine bakın.  
  
 C++ Standart Kitaplığı bileşenleri değişkenlerinde şablon eksik tarafından bu hatanın nedeni olabilir.  
  
 Aşağıdaki örnek C2976 oluşturur:  
  
```  
// C2976.cpp  
template <class T>   
struct TC {  
   T t;  
};  
int main() {  
   TC<>* t;   // C2976  
   TC<int>* t2;   // OK  
}  
```  
  
 Ayrıca C2976 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2976b.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC {  
   T t;  
};  
  
int main() {  
   GC<>^ g;   // C2976  
   GC<int>^ g2;   // OK  
}  
```