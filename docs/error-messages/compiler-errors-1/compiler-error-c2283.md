---
title: Derleyici hatası C2283
ms.date: 11/04/2016
f1_keywords:
- C2283
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
ms.openlocfilehash: 7f3568aa5dfee116a225256a4452465c05f72f6f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759158"
---
# <a name="compiler-error-c2283"></a>Derleyici hatası C2283

' Identifier ': saf belirtici veya soyut geçersiz kılma belirticisi adlandırılmamış yapıda kullanılamaz

Adlandırılmamış bir sınıfın veya yapının üye işlevi, bir saf belirtici ile tanımlanmış, buna izin verilmez.

Aşağıdaki örnek C2283 oluşturur:

```cpp
// C2283.cpp
// compile with: /c
struct {
   virtual void func() = 0;   // C2283
};
struct T {
   virtual void func() = 0;   // OK
};
```
