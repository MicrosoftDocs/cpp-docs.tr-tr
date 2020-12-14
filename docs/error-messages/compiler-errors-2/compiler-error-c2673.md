---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2673'
title: Derleyici hatası C2673
ms.date: 11/04/2016
f1_keywords:
- C2673
helpviewer_keywords:
- C2673
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
ms.openlocfilehash: 1b7d634e4c1b62860a648ef5327ffd8b888c7d7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282074"
---
# <a name="compiler-error-c2673"></a>Derleyici hatası C2673

' function ': genel işlevlerde ' this ' işaretçileri yoktur

Genel bir işlev erişmeye çalıştı **`this`** .

Aşağıdaki örnek C2673 oluşturur:

```cpp
// C2673.cpp
int main() {
   this = 0;   // C2673
}
```
