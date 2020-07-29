---
title: Derleyici Uyarısı (düzey 1) C4532
ms.date: 11/04/2016
f1_keywords:
- C4532
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
ms.openlocfilehash: b8c7503c7d1c1b711006415a327c360731222042
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87196350"
---
# <a name="compiler-warning-level-1-c4532"></a>Derleyici Uyarısı (düzey 1) C4532

' devam ': __finally/finally bloğunun dışına atlayın, sonlandırma işlemi sırasında tanımsız davranışa sahiptir

Derleyici aşağıdaki anahtar sözcüklerden biriyle karşılaştı:

- [devam](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

olağan dışı Sonlandırma sırasında [__finally](../../cpp/try-finally-statement.md) veya [finally](../../dotnet/finally.md) bloğunun dışına atlanmasına neden olur.

Bir özel durum oluşursa ve yığın sonlandırma işleyicilerinin yürütülmesi sırasında ( **`__finally`** ya da finally blokları) ve kodunuz, blok bitmeden önce bir bloğun dışına atlarken, **`__finally`** **`__finally`** davranış tanımsızdır. Denetim geri sarma koduna dönemeyebilir, bu nedenle özel durum düzgün işlenmeyebilir.

Bir bloktan birini atlamanız gerekiyorsa **`__finally`** önce olağan dışı sonlandırmasını denetleyin.

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
