---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2541'
title: Derleyici hatası C2541
ms.date: 11/04/2016
f1_keywords:
- C2541
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
ms.openlocfilehash: 79d4cab33a7c92455b5a4eacdf75f26f80b16a33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302016"
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
