---
title: Derleyici Uyarısı (düzey 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: d8769f5663ca0bde9048e52d4579012dfccab0a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532034"
---
# <a name="compiler-warning-level-1-c4288"></a>Derleyici Uyarısı (düzey 1) C4288

Standart olmayan uzantı kullanıldı: 'var': for döngüsünde bildirimi yapılan döngü denetim değişkeni for döngüsü kapsamının dışında; kullanılıyor Dış kapsamdaki bildirimiyle çakışıyor

İle derlerken [/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve **/Zc:forscope-**, içinde bildirilen bir değişken bir **için** döngü sonra kullanıldı [için](../../cpp/for-statement-cpp.md)-döngü kapsamı. C++ dili için bir Microsoft uzantısı kapsamında kalmak bu değişkeni verir ve C4288 değişkenin ilk bildirimi kullanılmaz anımsatır.

Bkz: [/ZC: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) Microsoft uzantısı'nda belirtme hakkında daha fazla bilgi için **için** döngüleri /Ze ile.

Aşağıdaki örnek, C4288 oluşturur:

```
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```