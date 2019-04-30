---
title: Derleyici Uyarısı (düzey 1) C4566
ms.date: 11/04/2016
f1_keywords:
- C4566
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
ms.openlocfilehash: c864feb2478e9f99ad6e4c0087dcef72b55de601
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397271"
---
# <a name="compiler-warning-level-1-c4566"></a>Derleyici Uyarısı (düzey 1) C4566

evrensel karakter adı 'char' temsil edilen karakter geçerli kod sayfasında (sayfa) gösterilemez

Her Unicode karakter geçerli ANSI kod sayfasında temsil edilebilir.

Çok geniş dizelerdir (iki baytlık karakter) ise korunmadığını dar dize (tek bayt karakterle) için çok baytlı karakter dönüştürülür.

Aşağıdaki örnek, C4566 oluşturur:

```
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```