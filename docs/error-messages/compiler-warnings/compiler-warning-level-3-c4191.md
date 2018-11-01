---
title: Derleyici Uyarısı (Düzey 3) C4191
ms.date: 11/04/2016
f1_keywords:
- C4191
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
ms.openlocfilehash: 72a485811647911207b6d048c686acdadd142b65
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657775"
---
# <a name="compiler-warning-level-3-c4191"></a>Derleyici Uyarısı (Düzey 3) C4191

' operator/operation': 'type of expression' öğesinden 'type required' güvenli olmayan dönüştürme

İşlev işaretçileri içeren çeşitli işlemleri güvenli olarak değerlendirilir:

- İşlev türleri farklı çağırma kurallarına sahip.

- İşlev türleri farklı olan dönüş kuralları.

- Bağımsız değişken veya return türlerinin farklı boyutlarda, türü kategorilerini ve sınıflandırmalarını ile.

- Farklı bağımsız değişken listesi uzunlukları (üzerinde `__cdecl`, yalnızca kısa listesi, hatta daha uzun listeden dönüştürme kısa ise varargs).

- Veri işaretçisine (dışında **void**<strong>\*</strong>) diğer adlı karşı işlevi işaretçisi.

- Üzerinde bir hata veya uyarı verir herhangi bir türü fark bir `reinterpret_cast`.

İşaretçi aracılığıyla bu işlevi çağırmak, programın çökmesine neden olabilir.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4191 oluşturur:

```
// C4191.cpp
// compile with: /W3 /clr
#pragma warning(default: 4191)

void __clrcall f1() { }
void __cdecl   f2() { }

typedef void (__clrcall * fnptr1)();
typedef void (__cdecl   * fnptr2)();

int main() {
   fnptr1 fp1 = static_cast<fnptr1>(&f1);
   fnptr2 fp2 = (fnptr2) &f2;

   fnptr1 fp3 = (fnptr1) &f2;   // C4191
   fnptr2 fp4 = (fnptr2) &f1;   // C4191
};
```