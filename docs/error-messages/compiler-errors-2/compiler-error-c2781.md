---
title: Derleyici Hatası C2781
ms.date: 11/04/2016
f1_keywords:
- C2781
helpviewer_keywords:
- C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
ms.openlocfilehash: be665d86cf230c364f522fd1ad74cd5a124ac9de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382977"
---
# <a name="compiler-error-c2781"></a>Derleyici Hatası C2781

'bildirim': en az bekliyor value1 bağımsız değişkeni - sağlanan value2

Değişken parametre listesine sahip bir işlev şablonu çok az sayıda bağımsız değişken var.

Aşağıdaki örnek, C2781 oluşturur:

```
// C2781.cpp
template<typename T>
void f(T, T, ...){}

int main() {
   f(1);   // C2781

   // try the following line instead
   f(1,1);
}
```