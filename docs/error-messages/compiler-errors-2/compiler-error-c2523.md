---
title: Derleyici hatası C2523
ms.date: 11/04/2016
f1_keywords:
- C2523
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
ms.openlocfilehash: 56b0f88949d7a7fa5af945ab5d03ee9a480d6d3f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746428"
---
# <a name="compiler-error-c2523"></a>Derleyici hatası C2523

' class:: ~ Identifier ': yıkıcı/Sonlandırıcı etiketi uyumsuzluğu

Yıkıcı adı, önünde bir tilde (`~`) olan sınıf adı olmalıdır. Oluşturucu ve yıkıcısı, sınıfla aynı ada sahip olan tek üyedir.

Aşağıdaki örnek C2523 oluşturur:

```cpp
// C2523.cpp
// compile with: /c
class A {
   ~B();    // C2523
   ~A();   // OK
};
```
