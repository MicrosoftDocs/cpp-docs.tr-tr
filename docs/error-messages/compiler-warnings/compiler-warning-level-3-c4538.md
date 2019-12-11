---
title: Derleyici Uyarısı (düzey 3) C4538
ms.date: 11/04/2016
f1_keywords:
- C4538
helpviewer_keywords:
- C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
ms.openlocfilehash: c68bcbfe035f12f1a2a16bbcaffbaf4db080388f
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992037"
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
