---
title: Derleyici Uyarısı (Düzey 3) C4414
ms.date: 11/04/2016
f1_keywords:
- C4414
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
ms.openlocfilehash: 0a9ceb332888e306b8cb3bcbe1832f773d02d63d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401949"
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