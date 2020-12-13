---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3289'
title: Derleyici hatası C3289
ms.date: 11/04/2016
f1_keywords:
- C3289
helpviewer_keywords:
- C3289
ms.assetid: 3c1c623b-7fcf-43ab-a89a-8722532a8d29
ms.openlocfilehash: 12c1f14d1760256f38f225c6215fd41de930d2c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144787"
---
# <a name="compiler-error-c3289"></a>Derleyici hatası C3289

' Property ': önemsiz bir özelliğin dizini oluşturulamaz

Bir özellik yanlış bildirildi. Dizin oluşturulmuş bir özellik için erişimcilerinin tanımlanması gerekir. Daha fazla bilgi için bkz. [özelliği](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3289 oluşturur.

```cpp
// C3289.cpp
// compile with: /clr
public ref struct C {
   // user-defined simple indexer
   property int indexer1[int];   // C3289

   // user-defined indexer
   property int indexer2[int] {
      int get(int i) { return 0; }
      void set(int i, int j) {}
   }
};

int main() {
   C ^ MyC = gcnew C();
   MyC->indexer2[0] = 1;
}
```
