---
title: Derleyici Uyarısı (düzey 1) C4288 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4288
dev_langs:
- C++
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8b9e82f8cb24c4635fb64c3ac0a1c82e301c086
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056500"
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