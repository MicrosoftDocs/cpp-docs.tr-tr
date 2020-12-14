---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3755'
title: Derleyici hatası C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: 24d6af223b6a15cbf1740bf67144250007c2091d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253591"
---
# <a name="compiler-error-c3755"></a>Derleyici hatası C3755

' Delegate ': bir temsilci tanımlanamaz

Bir [Temsilci (C++ Bileşen Uzantıları)](../../extensions/delegate-cpp-component-extensions.md) tanımlanmış ancak tanımlanmamış olabilir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C3755 oluşturur.

```cpp
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

C3755, bir temsilci şablonu oluşturmaya çalıştığınızda da oluşabilir. Aşağıdaki örnek C3755 oluşturur.

```cpp
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```
