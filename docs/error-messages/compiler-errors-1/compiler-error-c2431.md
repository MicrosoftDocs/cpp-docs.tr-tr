---
title: Derleyici hatası C2431
ms.date: 11/04/2016
f1_keywords:
- C2431
helpviewer_keywords:
- C2431
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
ms.openlocfilehash: 135f73490cf23313d4ac4e2a5f568f2b6100422b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744531"
---
# <a name="compiler-error-c2431"></a>Derleyici hatası C2431

' Identifier ' içinde geçersiz dizin kaydı

ESP kaydı ölçeklendirilir veya hem dizin hem de temel kayıt olarak kullanılır. X86 işlemcisinin SıB kodlaması, bunlardan birine izin vermez.

Aşağıdaki örnek C2431 oluşturur:

```cpp
// C2431.cpp
// processor: x86
int main() {
   _asm mov ax, [ESI + 2*ESP]   // C2431
   _asm mov ax, [esp + esp]   // C2431
}
```
