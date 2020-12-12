---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4142'
title: Derleyici Uyarısı (düzey 1) C4142
ms.date: 11/04/2016
f1_keywords:
- C4142
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
ms.openlocfilehash: d82403d79310d577cd45fe835cd486719ea0fdc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115735"
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
