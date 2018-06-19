---
title: Derleyici Uyarısı (düzey 1) C4733 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4733
dev_langs:
- C++
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59d702867fb4950b97ee2d2c6249c26229aac975
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281937"
---
# <a name="compiler-warning-level-1-c4733"></a>Derleyici Uyarısı (düzey 1) C4733
Satır içi asm 'FS:0' atama: işleyici güvenli işleyici olarak kayıtlı değil  
  
 İşleyicinin bir geçerli özel durum işleyici olarak kaydettirilmemiş olabilir yeni bir özel durum işleyicisi eklemek için FS:0 değerinde değiştirme işlevi güvenli istisnalar işe yaramayabilir, çünkü (bkz [SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)).  
  
 Bu uyarıyı çözmek için ya da FS:0 tanımı kaldırın veya bu uyarı etkinleştirmek ve kullanmak [. SAFESEH](../../assembler/masm/dot-safeseh.md) güvenli özel durum işleyicileri belirtmek için.  
  
 Aşağıdaki örnek C4733 oluşturur:  
  
```  
// C4733.cpp  
// compile with: /W1 /c  
// processor: x86  
#include "stdlib.h"  
#include "stdio.h"  
void my_handler()  
{  
   printf("Hello from my_handler\n");  
   exit(1);  
}  
  
int main()  
{  
   _asm {  
      push    my_handler  
      mov     eax, DWORD PTR fs:0  
      push    eax  
      mov     DWORD PTR fs:0, esp   // C4733  
   }  
  
   *(int*)0 = 0;  
}  
```