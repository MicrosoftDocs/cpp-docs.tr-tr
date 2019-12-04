---
title: Derleyici hatası C2541
ms.date: 11/04/2016
f1_keywords:
- C2541
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
ms.openlocfilehash: de24503d256b8c7649ce87969b1b2f6a4709ac8f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740851"
---
# <a name="compiler-error-c2541"></a>Derleyici hatası C2541

' Sil ': delete: işaretçi olmayan nesneler silinemez

[Delete](../../cpp/delete-operator-cpp.md) işleci, işaretçi olmayan bir nesne üzerinde kullanıldı.

Aşağıdaki örnek C2541 oluşturur:

```cpp
// C2541.cpp
int main() {
   int i;
   delete i;   // C2541 i not a pointer

   // OK
   int *ip = new int;
   delete ip;
}
```
