---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2389'
title: Derleyici hatası C2389
ms.date: 11/04/2016
f1_keywords:
- C2389
helpviewer_keywords:
- C2389
ms.assetid: 6122dc81-4ee3-49a5-a67d-d867808c9bac
ms.openlocfilehash: 1f9d34be47376564bf7c6fc221cf6f5b01e7850f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123974"
---
# <a name="compiler-error-c2389"></a>Derleyici hatası C2389

' operator ': geçersiz işleç ' nullptr '

**`nullptr`** bir işlenen olamaz.

Aşağıdaki örnek C2389 oluşturur:

```cpp
// C2389.cpp
// compile with: /clr
int main() {
   throw nullptr;   // C2389
}
```
