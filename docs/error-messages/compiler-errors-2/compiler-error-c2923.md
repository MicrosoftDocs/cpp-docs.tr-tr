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
ms.openlocfilehash: 84a0e844161ea13fdc2515fa6ea403adf2e5caa1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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