---
title: Derleyici Hatası C3623
ms.date: 11/04/2016
f1_keywords:
- C3623
helpviewer_keywords:
- C3623
ms.assetid: a0341b45-062a-4f67-beb9-ba74201ed1ed
ms.openlocfilehash: dd12e64e775807220b4ece1f4c26a2f52437c69e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221911"
---
# <a name="compiler-error-c3623"></a>Derleyici Hatası C3623

'variable': bit alanları desteklenmez yönetilen veya WinRT türleri

Bit alanlarını kullanma, yönetilen bir değişken veya WinRT sınıfı izin verilmez.

Aşağıdaki örnek, C3623 oluşturur:

```
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
