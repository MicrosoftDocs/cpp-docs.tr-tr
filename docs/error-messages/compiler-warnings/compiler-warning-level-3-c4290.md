---
title: "Derleyici Uyarısı (Düzey 3) C4290 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4290
dev_langs:
- C++
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f70a278cb3e660e89e1aba067cab9c20aacf8f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4290"></a>Derleyici Uyarısı (Düzey 3) C4290
C++ özel durum belirtimi bir işlevi belirtmek üzere dışında göz ardı __declspec(nothrow) değil  
  
 Bir işlev Visual C++ kabul eder, ancak uygulamayan özel durum belirtimi kullanılarak bildirildi. Derleme sırasında yok sayılır belirtimleri derlenmesi gerekebilir özel durumla kod ve bağlı olarak gelecekte özel durum belirtimleri destekleyen sürümler yeniden kullanılabilir.  
  
 Daha fazla bilgi için bkz: [özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md) .  
  
 Bu uyarı kullanarak önleyebilirsiniz [uyarı](../../preprocessor/warning.md) pragma:  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 Aşağıdaki kod örneği C4290 oluşturur:  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```