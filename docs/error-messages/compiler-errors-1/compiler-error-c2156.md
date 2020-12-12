---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2156'
title: Derleyici hatası C2156
ms.date: 11/04/2016
f1_keywords:
- C2156
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
ms.openlocfilehash: fa9954c52be278442d357dfa69071f83d10e49e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204140"
---
# <a name="compiler-error-c2156"></a>Derleyici hatası C2156

pragma işlevin dışında olmalıdır

Genel düzeyde (bir işlev gövdesi dışında) belirtilmesi gereken bir pragma, bir işlev içinde.

Aşağıdaki örnek C2156 oluşturur:

```cpp
// C2156.cpp
#pragma optimize( "l", on )   // OK
int main() {
   #pragma optimize( "l", on )   // C2156
}
```
