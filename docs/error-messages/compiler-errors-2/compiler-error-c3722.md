---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3722'
title: Derleyici hatası C3722
ms.date: 11/04/2016
f1_keywords:
- C3722
helpviewer_keywords:
- C3722
ms.assetid: 3cb28363-5eff-4548-bd0d-d5c615846353
ms.openlocfilehash: 6f24a480f4488ebb910921afe88fe03f54e957b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239031"
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
