---
title: Derleyici hatası C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: f1f73e2585606e7e86213607a96ef713345419c1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755414"
---
# <a name="compiler-error-c2588"></a>Derleyici hatası C2588

':: ~ Identifier ': geçersiz genel yıkıcı

Yıkıcı, bir sınıf, yapı veya birleşim dışında bir öğe için tanımlanır. Buna izin verilmez.

Bu hata, kapsam çözümleme (`::`) işlecinin sol tarafındaki eksik bir sınıf, yapı veya birleşim adından kaynaklanabilir.

Aşağıdaki örnek C2588 oluşturur:

```cpp
// C2588.cpp
~F();   // C2588
```
