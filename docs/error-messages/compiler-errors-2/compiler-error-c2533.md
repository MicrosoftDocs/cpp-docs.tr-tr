---
title: Derleyici Hatası C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 00cb13d1999b00dfcaa5a2bc7bfb3b8eb16af5f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661883"
---
# <a name="compiler-error-c2533"></a>Derleyici Hatası C2533

'identifier': oluşturucuların bir dönüş türüne izin verilmiyor

Oluşturucusu bir dönüş türü olamaz (değil bile bir `void` dönüş türü).

Bu hatanın yaygın bir kaynağı bir sınıf tanımının son ve ilk Oluşturucu uygulaması arasında eksik noktalı virgüldür. Derleyici, sınıf oluşturucu işlevi için dönüş türü tanımı olarak görür ve C2533 oluşturur.

Aşağıdaki örnek, C2533 oluşturur ve bu sorunun nasıl gösterir:

```
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```