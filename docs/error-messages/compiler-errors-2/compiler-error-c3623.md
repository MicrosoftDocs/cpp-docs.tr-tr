---
title: Derleyici hatası C3623
ms.date: 11/04/2016
f1_keywords:
- C3623
helpviewer_keywords:
- C3623
ms.assetid: a0341b45-062a-4f67-beb9-ba74201ed1ed
ms.openlocfilehash: 5d83e75d46fb078db3e74bf389563ca2ff34bb61
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740877"
---
# <a name="compiler-error-c3623"></a>Derleyici hatası C3623

' Variable ': bit alanları yönetilen veya WinRT türlerinde desteklenmiyor

Yönetilen veya WinRT sınıfındaki değişkenlerde bit alanlarının kullanılmasına izin verilmez.

Aşağıdaki örnek C3623 oluşturur:

```cpp
// C3623.cpp
// compile with: /clr
using namespace System;
ref class CMyClass {
public:
   int i : 1;   // C3623
};

int main() {
   CMyClass^ pMyClass = gcnew CMyClass();
   pMyClass->i = 3;
   Console::Out->WriteLine(pMyClass->i);
}
```
