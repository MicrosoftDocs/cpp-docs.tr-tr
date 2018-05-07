---
title: Derleyici Hatası C3149 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3149
dev_langs:
- C++
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c0441a7aebf86139aedbd5e45a7645db0a90b37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3149"></a>Derleyici Hatası C3149
'type': Bu tür burada en üst düzey 'char' olmadan kullanılamaz  
  
 Bir bildirim doğru şekilde belirtilmedi.  
  
 Örneğin, genel kapsamlı bir CLR türü tanımlı ve türünde bir değişken tanımının bir parçası oluşturmayı denedi. CLR türleri, Global değişkenler izin verilmediğinden derleyici C3149 oluşturur.  
  
 Bu hatayı gidermek için CLR türleri bir işlevi veya türü tanımı içinde değişkenleri bildirin.  
  
 Aşağıdaki örnek C3149 oluşturur:  
  
```  
// C3149.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   // declare an array of value types   
   array< Int32 ^> IntArray;   // C3149  
   array< Int32>^ IntArray2;   // OK  
}  
```  
  
 Aşağıdaki örnek C3149 oluşturur:  
  
```  
// C3149b.cpp  
// compile with: /clr /c  
delegate int MyDelegate(const int, int);  
void Test1(MyDelegate m) {}   // C3149  
void Test2(MyDelegate ^ m) {}   // OK  
```  
