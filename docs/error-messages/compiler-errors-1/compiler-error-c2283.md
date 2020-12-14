---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2283'
title: Derleyici hatası C2283
ms.date: 11/04/2016
f1_keywords:
- C2283
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
ms.openlocfilehash: dab8688623962051759f9f4be84f5831b58a700f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294983"
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
