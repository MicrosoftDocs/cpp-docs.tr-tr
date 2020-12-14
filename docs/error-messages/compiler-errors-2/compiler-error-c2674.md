---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2674'
title: Derleyici hatası C2674
ms.date: 11/04/2016
f1_keywords:
- C2674
helpviewer_keywords:
- C2674
ms.assetid: 7cbd70d8-d992-44d7-a5cb-dd8cf9c759d2
ms.openlocfilehash: c88a32eaeeda28b8ffb8daa0411a71fd773ffa2b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282051"
---
# <a name="compiler-error-c2674"></a>Derleyici hatası C2674

Bu bağlamda genel bildirime izin verilmez

Genel yanlış bildirildi. Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2674 oluşturur.

```cpp
// C2674.cpp
// compile with: /clr /c
void F(generic <class T> ref class R1);   // C2674
generic <class T> ref class R2 {};   // OK
```
