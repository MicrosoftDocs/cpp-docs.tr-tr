---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3828'
title: Derleyici hatası C3828
ms.date: 11/04/2016
f1_keywords:
- C3828
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
ms.openlocfilehash: 90c731ffc636355b5c9a1963facbcccabf356700
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249327"
---
# <a name="compiler-error-c3828"></a>Derleyici hatası C3828

' nesne türü ': yönetilen veya Wınrtclass örnekleri oluşturulurken yerleştirme bağımsız değişkenlerine izin verilmez

Yönetilen bir tür veya Windows Çalışma Zamanı türünde bir nesne oluştururken, [New, gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md) veya [New](../../cpp/new-operator-cpp.md)işleç başvurusunun yerleştirme formunu kullanamazsınız.

Aşağıdaki örnek C3828 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3828a.cpp
// compile with: /clr
ref struct M {
};

ref struct N {
   static array<char>^ bytes = gcnew array<char>(256);
};

int main() {
   M ^m1 = new (&N::bytes) M();   // C3828
   // The following line fixes the error.
   // M ^m1 = gcnew M();
}
```
