---
title: Derleyici Uyarısı (düzey 1) C4142
ms.date: 11/04/2016
f1_keywords:
- C4142
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
ms.openlocfilehash: 762f52c9f051a660cce68d424e02fc45422376e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456088"
---
# <a name="compiler-warning-level-1-c4142"></a>Derleyici Uyarısı (düzey 1) C4142

tür zararsız olarak yeniden tanımlanması

Bir tür, oluşturulan kod üzerinde hiçbir etkisi bir şekilde tanımlandı.

Aşağıdaki olası nedenleri kontrol ederek düzeltmek için:

- Türetilmiş bir sınıfın üye işlevi, temel sınıfın farklı dönüş türü karşılık gelen bir üye işlevi olan.

- İle tanımlanan bir tür `typedef` komutu yeniden farklı söz dizimini kullanarak.

Aşağıdaki örnek, C4142 oluşturur:

```
// C4142.c
// compile with: /W1
float X2;
X2 = 2.0 + 1.0;   // C4142

int main() {
   float X2;
   X2 = 2.0 + 1.0;   // OK
}
```