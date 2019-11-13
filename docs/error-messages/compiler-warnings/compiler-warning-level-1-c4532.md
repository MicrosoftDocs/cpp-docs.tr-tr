---
title: Derleyici Uyarısı (düzey 1) C4532
ms.date: 11/04/2016
f1_keywords:
- C4532
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
ms.openlocfilehash: b47eb192bc01e6fe2c6c9423ed2c672f16c6818f
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966244"
---
# <a name="compiler-warning-level-1-c4532"></a>Derleyici Uyarısı (düzey 1) C4532

' devam ': __finally/finally bloğunun dışına atlayın, sonlandırma işlemi sırasında tanımsız davranışa sahiptir

Derleyici aşağıdaki anahtar sözcüklerden biriyle karşılaştı:

- [continue](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

olağan dışı Sonlandırma sırasında [__finally](../../cpp/try-finally-statement.md) veya [finally](../../dotnet/finally.md) bloğunun dışına atlanmasına neden olur.

Bir özel durum oluşursa ve yığın sonlandırma işleyicilerinin yürütülmesi sırasında (`__finally` ya da finally blokları) ve kodunuz, `__finally` bloğu bitmeden önce bir `__finally` bloğunun dışına atlarken, davranış tanımsızdır. Denetim geri sarma koduna dönemeyebilir, bu nedenle özel durum düzgün işlenmeyebilir.

**__Finally** bloğundan birini atlamanız gerekiyorsa, önce olağan dışı sonlandırmasını denetleyin.

Aşağıdaki örnek C4532 oluşturur; uyarıları çözümlemek için, sıçrama deyimlerini açıklama olarak belirlemeniz yeterlidir.

```cpp
// C4532.cpp
// compile with: /W1
// C4532 expected
int main() {
   int i;
   for (i = 0; i < 10; i++) {
      __try {
      } __finally {
         // Delete the following line to resolve.
         continue;
      }

      __try {
      } __finally {
         // Delete the following line to resolve.
         break;
      }
   }
}
```