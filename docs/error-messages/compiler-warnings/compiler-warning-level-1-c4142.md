---
title: Derleyici Uyarısı (düzey 1) C4142
ms.date: 11/04/2016
f1_keywords:
- C4142
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
ms.openlocfilehash: 3c9ab9c22d41e7732c86d43f5c6b4f09c50bbda8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87196857"
---
# <a name="compiler-warning-level-1-c4142"></a>Derleyici Uyarısı (düzey 1) C4142

tür için zararsız yeniden tanımlama

Bir tür, oluşturulan kod üzerinde hiçbir etkisi olmayacak şekilde yeniden tanımlanır.

Aşağıdaki olası nedenleri denetleyerek onarmak için:

- Türetilmiş bir sınıfın üye işlevi, temel sınıfın karşılık gelen üye işlevinden farklı bir dönüş türüne sahiptir.

- Komutuyla tanımlanan bir tür, **`typedef`** farklı sözdizimi kullanılarak yeniden tanımlandı.

Aşağıdaki örnek C4142 oluşturur:

```c
// C4142.c
// compile with: /W1
float X2;
X2 = 2.0 + 1.0;   // C4142

int main() {
   float X2;
   X2 = 2.0 + 1.0;   // OK
}
```
