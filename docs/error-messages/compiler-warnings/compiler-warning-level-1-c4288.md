---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4288'
title: Derleyici Uyarısı (düzey 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: 827dd357aa4504c9f806cbcbe534ae45ccaf33b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311727"
---
# <a name="compiler-warning-level-1-c4288"></a>Derleyici Uyarısı (düzey 1) C4288

> Standart olmayan uzantı kullanıldı: ' var ': for döngüsünde belirtilen döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor; Dış kapsamdaki bildirimle çakışıyor

İle derleme yaparken [`/Ze`](../../build/reference/za-ze-disable-language-extensions.md) ve **/Zc: forScope-**, **`for`** [for](../../cpp/for-statement-cpp.md)döngüsü kapsamından sonra döngüde belirtilen bir değişken kullanıldı. C++ diline yönelik bir Microsoft uzantısı, bu değişkenin kapsamda kalmasına izin verir ve C4288, değişkenin ilk bildiriminin kullanılmadığını hatırlatır.

[`/Zc:forScope`](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)Microsoft uzantısını **`for`** /Zeile Döngülerde belirtme hakkında bilgi için bkz..

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
