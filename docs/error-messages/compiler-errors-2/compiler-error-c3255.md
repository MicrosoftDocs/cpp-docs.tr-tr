---
title: "Derleyici Hatası C3255 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3255
dev_langs: C++
helpviewer_keywords: C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 86052e8ffa7e9ba9627a290318dbe6115af3d36c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3255"></a>Derleyici Hatası C3255
'değer türü': dinamik olarak bu değer türü nesnesi yerel yığında tahsis edilemiyor  
  
 Değer türü örnekleri (bkz [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md)) yönetilen üyeleri içeren yığında ancak öbek oluşturulabilir.  
  
 Aşağıdaki örnek C3255 oluşturur:  
  
```  
// C3255.cpp  
// compile with: /clr  
using namespace System;  
value struct V {  
   Object^ o;  
};  
  
value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = new V;   // C3255  
   V2* pv2 = new V2;  
   V v2;  
}  
```  
