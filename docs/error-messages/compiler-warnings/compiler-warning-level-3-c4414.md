---
title: Derleyici Uyarısı (Düzey 3) C4414 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4414
dev_langs:
- C++
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd0868fea89cd868178956c0aba171ce6525bd75
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043215"
---
# <a name="compiler-warning-level-3-c4414"></a>Derleyici Uyarısı (Düzey 3) C4414

'function': işleve yönelik kısa atlama yakın olarak dönüştürüldü

Kısa atlama hangi sınırlı bir aralıkta bir adres için yönergesinden dallar compact yönerge oluşturur. Yönergenin bağlantı hedef adresi, işlev tanımı arasındaki uzaklığı gösteren kısa bir uzaklık içerir. Bağlama sırasında bir işlev, işlev erişilebilir aralık dışında bir kısa uzaklığı taşınmasına neden taşınmış ya da konu için bağlama zamanı iyileştirmeleri olabilir. Derleyicinin yakın veya uzak jmp yönerge gerektiren atlama için özel bir kaydı oluşturmanız gerekir. Derleyici, dönüştürme yapılır.

Örneğin, aşağıdaki kod C4414 oluşturur:

```
// C4414.cpp
// compile with: /W3 /c
// processor: x86
int DoParityEven();
int DoParityOdd();
unsigned char global;
int __declspec(naked) DoParityEither()
{
   __asm
   {
      test global,0
      jpe SHORT DoParityEven  // C4414
      jmp SHORT DoParityOdd   // C4414
   }
}
```