---
title: Derleyici Uyarısı (Düzey 3) C4290 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4290
dev_langs:
- C++
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f03d35e1a3756979d8936647255e2b65afef56d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289899"
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