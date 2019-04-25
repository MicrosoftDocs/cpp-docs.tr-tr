---
title: Derleyici Uyarısı (düzey 1) C4532
ms.date: 11/04/2016
f1_keywords:
- C4532
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
ms.openlocfilehash: bcadf31eda079ebb8ea7a496efe4c945e16b1ab7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160763"
---
# <a name="compiler-warning-level-1-c4532"></a>Derleyici Uyarısı (düzey 1) C4532

'continue': __finally/finally bloğunun dışına atlama sonlandırma işleme sırasında davranışı tanımsız

Derleyici, aşağıdaki anahtar sözcükler birini karşılaştı:

- [continue](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

dışında bir atlama neden bir [__finally](../../cpp/try-finally-statement.md) veya [son](../../dotnet/finally.md) olağan dışı sonlandırma sırasında blok.

Bir özel durum oluşursa ve yığın sonlandırma işleyicileri yürütülürken sapmasına sırada ( `__finally` veya finally bloklarında), ve kod dışı atlar bir `__finally` önce block `__finally` blok uç, davranış tanımlanmamıştır. Özel durumu düzgün bir şekilde işlenmemiş için denetimi geriye doğru izleme kodu döndürmeyebilir.

/ Atlama, bir **__finally** engelleme, olağan dışı sonlandırma için ilk olarak denetleyin.

Aşağıdaki örnek, C4532 oluşturur; Yalnızca açıklama uyarıları gidermek için atlama deyimleri yerleştirin.

```
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