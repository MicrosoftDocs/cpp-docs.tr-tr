---
title: "Derleyici Hatası C2783 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2783
dev_langs: C++
helpviewer_keywords: C2783
ms.assetid: 1ce94a11-bb8b-4be3-a222-f1f105da74b3
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86f8c8aff0974cc1908c38bd8b44b26af4812278
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2783"></a>Derleyici Hatası C2783
'bildirimi': 'tanımlayıcısı' için şablon bağımsız değişken türetme değil  
  
 Derleyici şablon bağımsız değişken belirleyemiyor. Varsayılan bağımsız değişkenler, bir şablon bağımsız değişken türetme için kullanılamaz.  
  
 Aşağıdaki örnek C2783 oluşturur:  
  
```  
// C2783.cpp  
template<typename T1, typename T2>  
T1 f(T2) {  
   return 248;  
}  
  
int main() {  
   f(1);   // C2783  
   // try the following line instead  
   int i = f<int>(1);  
}  
```  
  
 Ayrıca C2783 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2783b.cpp  
// compile with: /clr  
using namespace System;  
generic<typename T1, typename T2>   
T1 gf(T2) {  
   T1 t1 = safe_cast<T1>( Activator::CreateInstance(T1::typeid));  
   return t1;  
}  
  
ref class MyClass{};  
  
int main() {  
   int i;  
   i = gf(9);   // C2783  
  
   // OK  
   i = gf<int>(9);  
}  
```