---
title: Derleyici Hatası C2561 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2561
dev_langs:
- C++
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f8ece9a3d9347a5179844cbfca3425870c25e2f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2561"></a>Derleyici Hatası C2561
'tanımlayıcısı': işlevi bir değer döndürmesi gerekir  
  
 İşlev değer döndürme olarak bildirildi, ancak işlev tanımı içermiyor bir `return` deyimi.  
  
 Bu hata yanlış işlev prototipi tarafından kaynaklanabilir:  
  
1.  İşlevi bir değer döndürmezse, işlevin dönüş türüyle bildirme [void](../../cpp/void-cpp.md).  
  
2.  İşlev'in tüm olası dalları prototip bildirilen türü değeri döndürür denetleyin.  
  
3.  Dönüş değeri depolamak satır içi derleme yordamları içeren C++ işlevlerini `AX` kaydı bir dönüş ifadesi gerekebilir. Değer kopyalama `AX` geçici bir değişken için ve bu değişkeni işlevinden döndürür.  
  
 Aşağıdaki örnek C2561 oluşturur:  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```