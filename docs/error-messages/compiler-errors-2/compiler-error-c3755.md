---
title: Derleyici hatası C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: cc4e5423dc8fc53a8f749e2392ff23658a0cb0f1
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685121"
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
