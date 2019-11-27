---
title: Derleyici Uyarısı (düzey 3) C4538
ms.date: 11/04/2016
f1_keywords:
- C4538
helpviewer_keywords:
- C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
ms.openlocfilehash: b60d919952b07e63d28a373414f1307d2031f00d
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188954"
---
# <a name="compiler-warning-level-3-c4538"></a>Derleyici Uyarısı (düzey 3) C4538

' Type ': Bu tür üzerindeki const/volatile niteleyicileri desteklenmiyor

Bir niteleyici anahtar sözcüğü bir diziye yanlış uygulandı. Daha fazla bilgi için bkz. [dizi](../../extensions/arrays-cpp-component-extensions.md).

Aşağıdaki örnek C4538 oluşturur:

```cpp
// C4538.cpp
// compile with: /clr /W3 /LD
const array<int> ^f1();   // C4538
array<const int> ^f2();   // OK
```