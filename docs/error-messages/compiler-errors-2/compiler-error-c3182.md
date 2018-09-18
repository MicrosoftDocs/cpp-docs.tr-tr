---
title: Derleyici Hatası C3182 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3182
dev_langs:
- C++
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 722f95b41f9f5ec467af25ccf927631590f90e45
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110230"
---
# <a name="compiler-error-c3182"></a>Derleyici Hatası C3182

'class': bir üye bildirim kullanımı veya erişim bildirimi yönetilen veya WinRTtype içinde geçersiz

A [kullanarak](../../cpp/using-declaration.md) bildirimi tüm yönetilen sınıflar formları içinde geçersiz.

Aşağıdaki örnek, C3182 oluşturur ve bu sorunun nasıl gösterir.

```
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
