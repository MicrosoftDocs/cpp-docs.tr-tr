---
title: "Derleyici Hatası C3149 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3149
dev_langs: C++
helpviewer_keywords: C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dc5abf02a3210ca3d7bd858662e0c02d4f42d75d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
