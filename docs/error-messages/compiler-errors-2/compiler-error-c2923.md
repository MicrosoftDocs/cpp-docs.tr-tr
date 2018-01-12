---
title: "Derleyici Hatası C2923 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2923
dev_langs: C++
helpviewer_keywords: C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ac40932aaabb711a1f4088fc48280a1c18c3696
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2923"></a>Derleyici Hatası C2923
'type': 'tanımlayıcısı' parametresi 'param' için geçerli bir şablon tür bağımsız değişkeni değil  
  
 Bağımsız değişken listesi şablonu veya genel örneği oluşturmak için gereken bir türü eksik. Şablon ya da genel bildirimi denetleyin.  
  
 Aşağıdaki örnek C2923 oluşturur:  
  
```  
// C2923.cpp  
template <class T> struct TC {};  
int x;  
int main() {  
   TC<x>* tc2;   // C2923  
   TC<int>* tc2;   // OK  
}  
```  
  
 Ayrıca C2923 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2923b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC {};  
  
int x;  
  
int main() {  
   GC<x>^ gc2;   // C2923  
   GC<int>^ gc2;   // OK  
}  
```