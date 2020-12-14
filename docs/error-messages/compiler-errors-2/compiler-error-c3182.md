---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3182'
title: Derleyici hatası C3182
ms.date: 11/04/2016
f1_keywords:
- C3182
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
ms.openlocfilehash: d4cf5d86a553a597636c09f72ff3a068e2a6b9b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242034"
---
# <a name="compiler-error-c3182"></a>Derleyici hatası C3182

' class ': bir üye using bildirimi veya erişim bildirimi yönetilen veya Wınrttype içinde geçersizdir

[Using](../../cpp/using-declaration.md) bildirimi, yönetilen sınıfların tüm formlarında geçersizdir.

Aşağıdaki örnek C3182 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C3182a.cpp
// compile with: /clr /c
ref struct B {
   void mf(int) {
   }
};

ref struct D : B {
   using B::mf;   // C3182, delete to resolve
   void mf(char) {
   }
};
```
