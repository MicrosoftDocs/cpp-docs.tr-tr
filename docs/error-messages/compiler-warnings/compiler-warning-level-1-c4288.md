---
title: Derleyici Uyarısı (düzey 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: e706a448f4264eceedbb4fa8932c0fc30e88d532
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175746"
---
# <a name="compiler-warning-level-1-c4288"></a>Derleyici Uyarısı (düzey 1) C4288

Standart olmayan uzantı kullanıldı: ' var ': for döngüsünde belirtilen döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor; Dış kapsamdaki bildirimle çakışıyor

[/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve **/Zc: forScope**ile derlerken, **for döngüsünde belirtilen bir değişken** [for](../../cpp/for-statement-cpp.md)döngüsü kapsamından sonra kullanılır. C++ Dile yönelik bir Microsoft uzantısı, bu değişkenin kapsamda kalmasına izin verir ve C4288, değişkenin ilk bildiriminin kullanılmadığını hatırlatır.

Bkz. [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) , Microsoft uzantısını/Zeile döngüler **için** ' de belirtme hakkında bilgi için.

Aşağıdaki örnek C4288 oluşturur:

```cpp
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```
