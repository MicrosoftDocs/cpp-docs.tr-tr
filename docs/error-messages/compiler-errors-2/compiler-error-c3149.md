---
title: "Derleyici Hatası C3149 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3149
dev_langs:
- C++
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 154ae99c5e47438f6fca3b85ac8318c1b14f7a30
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
