---
title: Derleyici hatası C3698
ms.date: 11/04/2016
f1_keywords:
- C3698
helpviewer_keywords:
- C3698
ms.assetid: 3c02fb08-7ba4-4637-a06f-19926cb2b5f1
ms.openlocfilehash: 29c1df618d6a8a14f441c09a6db0f9457133910b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758053"
---
# <a name="compiler-error-c3698"></a>Derleyici hatası C3698

' Type ': Bu tür ' operator ' bağımsız değişkeni olarak kullanılamaz

Yönetilen bir nesne yanlış bildirildi.

Aşağıdaki örnek C3698 oluşturur:

```cpp
// C3698.cpp
// compile with: /clr

int main() {
   array<int>^a = new array<int>^(20);   // C3698
   array<int>^a2 = gcnew array<int>(20);   // OK
}
```
