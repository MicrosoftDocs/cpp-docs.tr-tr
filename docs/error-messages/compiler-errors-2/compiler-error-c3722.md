---
title: Derleyici hatası C3722
ms.date: 11/04/2016
f1_keywords:
- C3722
helpviewer_keywords:
- C3722
ms.assetid: 3cb28363-5eff-4548-bd0d-d5c615846353
ms.openlocfilehash: 08087b9cec0a48f0e439d6a2ff9fbe5f4e58d709
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753100"
---
# <a name="compiler-error-c3722"></a>Derleyici hatası C3722

genel bir olaya izin verilmez

Derleyici yalnızca genel sınıflara, yapılara ve işlevlere izin verir.  Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md).

Aşağıdaki örnek C3722 oluşturur:

```cpp
// C3722.cpp
// compile with: /clr
generic <typename T>
public delegate void MyEventHandler(System::Object^ sender, System::EventArgs^ e, T optional);

generic <class T>
public ref struct MyButton {
   generic<typename U>
   event MyEventHandler<U>^ Click;   // C3722
};
```
